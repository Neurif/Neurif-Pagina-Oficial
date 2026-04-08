<script>
import  { onMount } from 'svelte'
let visionRef
let visionProgress = 0

function updateVisionProgress() {
    if (!visionRef) return
    const rect = visionRef.getBoundingClientRect()
    const windowHeight = window.innerHeight || document.documentElement.clientHeight
    const progress = 1 - rect.top / windowHeight
    visionProgress = Math.min(Math.max(progress, 0), 1)
}

onMount(() => {
    updateVisionProgress()
    window.addEventListener('scroll', updateVisionProgress, { passive: true })
    window.addEventListener('resize', updateVisionProgress)
    return () => {
    window.removeEventListener('scroll', updateVisionProgress)
    window.removeEventListener('resize', updateVisionProgress)
    }
})


</script>

<div
  class="la_vision"
  bind:this={visionRef}
  style="opacity: {visionProgress}; transform: translateY({30 - visionProgress * 30}px); visibility: {visionProgress > 0 ? 'visible' : 'hidden'};"
>
  <h1>Nuestra Visión</h1>
  <p>Ser la empresa líder en el mercado de remodelaciones y tecnología estructural 
    al igual que en el apartado de seguridad cibernética. </p>
</div>

<style>
.la_vision {
  opacity: 0;
  visibility: hidden;
  transform: translateY(30px);
  transition: opacity 0.2s ease, transform 0.2s ease;
}
</style>
