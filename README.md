<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@3.12.0/dist/tf.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/coco-ssd@3.12.0/dist/coco-ssd.min.js"></script>
async function detectObjectsInVideo(videoElement) {
  const model = await cocoSsd.load();
  const canvas = document.createElement('canvas');
  const context = canvas.getContext('2d');
  
  async function detectFrame() {
    context.drawImage(videoElement, 0, 0, canvas.width, canvas.height);
    const predictions = await model.detect(canvas);
    
    // Aquí puedes realizar acciones basadas en las predicciones, como verificar si hay un objeto dentro de otro objeto.
    
    requestAnimationFrame(detectFrame);
  }
  
  detectFrame();
}
const videoElement = document.getElementById('video');
detectObjectsInVideo(videoElement);

