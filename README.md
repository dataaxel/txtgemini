# txtgemini
Denna Repoistory skall testa att köra filer ocj modeller via gemini.
Jag väntar på output därifrån.
260118 - Blir säkert versionsstrul
Precis som tänkt.

Nu skall colab-filen
Gemini_textklass_web_från_fil.ipynb

Vara uppdaterad för konfikten medllan Kears 3 och Tensorflow 2.
Felet med
 Samt kollar om:

An InputLayer should be passed either a `batchInputShape` or an `inputShape`. 

Observera att uppdatera rad 39 i index.htmal för att rensa cache av gamla modeller


    // --- INSTÄLLNINGAR ---
    // Om du laddade upp hela mappen 'tfjs_model' på GitHub, ändra raden nedan till:
    const MODEL_PATH = 'tfjs_model/';
    //const MODEL_PATH = ''; 
    // ---------------------
    // Ändrad 22.20 - 260118
    // Uppdaterad Colab-fil. Skall fixa input-length. Jaja

    // Det här är ett känt och frustrerande problem som beror på en versionskrock. 
    // Google Colab har nyligen uppdaterat till Keras 3, men TensorFlow.js förväntar sig formatet från Keras 2. 
    // Därför "glömmer" den bort input-formen i exporten oavsett hur tydligt man skriver koden.
    
    async function loadModel() {
        const statusEl = document.getElementById('loadingStatus');
        const btn = document.getElementById('analyzeBtn');
        const errBox = document.getElementById('errorBox');

        try {
            // Bygg sökvägar
            // Skall ändras enligt Gemini Brute_force för versionskonfikten Keras och tensorflow
            // 
            const modelUrl = MODEL_PATH + 'model.json?v=fixed2';
            // const modelUrl = MODEL_PATH + 'model.json';
            const metadataUrl = MODEL_PATH + 'metadata.json';
