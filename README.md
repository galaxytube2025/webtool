async function transcribeAudio(videoFile) {
  const formData = new FormData();
  formData.append('file', videoFile);
  
  const response = await fetch('https://api.openai.com/v1/audio/transcriptions', {
    method: 'POST',
    headers: {
      'Authorization': `Bearer ${OPENAI_KEY}`,
    },
    body: formData
  });
  
  return response.json();
}
