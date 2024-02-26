<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@3.12.0/dist/tf.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/coco-ssd@3.12.0/dist/coco-ssd.min.js"></script>
async function detectObjectsInVideo(https://thimbles.onlyplaygames.net/?sid=76d5dfec1e70cb9f49c2e9f918af645acb64262890caf55748509ab02eee69d6dfac671d8471f9cb364bf81667a0978197534c607be5a7f0562ca4e7f247ccfa&gid=39306323&api=api-eu.ig-onlyplay.net/api&pid=1&launchedForPid=1&params=eyJzaWQiOiI3NmQ1ZGZlYzFlNzBjYjlmNDljMmU5ZjkxOGFmNjQ1YWNiNjQyNjI4OTBjYWY1NTc0ODUwOWFiMDJlZWU2OWQ2ZGZhYzY3MWQ4NDcxZjljYjM2NGJmODE2NjdhMDk3ODE5NzUzNGM2MDdiZTVhN2YwNTYyY2E0ZTdmMjQ3Y2NmYSIsImdpZCI6IjM5MzA2MzIzIiwiYXBpIjoiYXBpLWV1LmlnLW9ubHlwbGF5Lm5ldFwvYXBpIiwicGlkIjoiMSIsImxhdW5jaGVkRm9yUGlkIjoiMSJ9) {
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

