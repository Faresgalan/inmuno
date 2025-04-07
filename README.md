# Inmuno
Cuestionario

<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Examen Interactivo</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; background: #f4f4f4; }
    .question-container { background: white; padding: 20px; margin-bottom: 20px; border-radius: 10px; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
    .correct { color: green; font-weight: bold; }
    .incorrect { color: red; font-weight: bold; }
    button { margin-top: 10px; }
  </style>
</head>
<body>

  <h1>Examen Interactivo</h1>
  <div id="quiz-container"></div>

  <script>
    const preguntas = [
    {
  pregunta: "¿En qué parte de los ganglios se genera el factor quimiotractante de los LsB?",
  opciones: ["En los folículos linfoides de los ganglios linfáticos", "En la médula ósea", "En el bazo"],
  respuesta: 0
},
{
  pregunta: "¿Cómo se llaman las proteínas que producen LsB?",
  opciones: ["Interleucinas", "Citocinas", "Inmunoglobulinas A, E, G, M, D"],
  respuesta: 2
},
{
  pregunta: "Al unirse a la superficie de la MO, ¿en qué se convierten los LsB?",
  opciones: ["LsB de memoria", "LsB MZ (Marginal zone)", "Células plasmáticas"],
  respuesta: 1
},
{
  pregunta: "¿Qué inmunoglobulinas están unidas a la superficie del LsB?",
  opciones: ["IgE e IgA", "IgD e IgM", "IgG e IgA"],
  respuesta: 1
},
{
  pregunta: "¿Dónde se encuentran los LsB de zona marginal?",
  opciones: ["En el timo", "En la médula ósea", "En el bazo"],
  respuesta: 2
},
{
  pregunta: "¿Qué significa PAMPs?",
  opciones: [
    "Proteínas asociadas a macrófagos",
    "Moléculas asociadas a patógenos",
    "Mecanismos de activación linfoide"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué tipo de LsB recuerdan al antígeno?",
  opciones: ["LsB plasmáticos", "LsB de memoria", "LsB zona marginal"],
  respuesta: 1
},
{
  pregunta: "¿A quién presenta el Ag el LsB?",
  opciones: ["A LsT CD8", "A macrófagos", "A Linfocito CD4"],
  respuesta: 2
},
{
  pregunta: "¿Cuál es la inmunoglobulina que actúa en mucosas como dímero?",
  opciones: ["IgG", "IgE", "IgA"],
  respuesta: 2
},
{
  pregunta: "¿Qué Ig atraviesa la placenta en el tercer trimestre?",
  opciones: ["IgG", "IgA", "IgM"],
  respuesta: 0
},
{
  pregunta: "¿Cuál es la inmunoglobulina más abundante en plasma?",
  opciones: ["IgE", "IgA", "IgG"],
  respuesta: 2
},
{
  pregunta: "¿Cuál Ig se eleva en las alergias?",
  opciones: ["IgE", "IgG", "IgM"],
  respuesta: 0
},
{
  pregunta: "¿Qué virus infecta LsB a través de sus receptores?",
  opciones: ["Virus de Epstein-Barr", "Citomegalovirus", "Virus de la hepatitis B"],
  respuesta: 0
},
{
  pregunta: "¿En qué se transforma el linfocito B activado?",
  opciones: ["Macrófago", "Célula plasmática", "Célula dendrítica"],
  respuesta: 1
},
{
  pregunta: "¿Cuáles son tres estructuras de los anticuerpos?",
  opciones: [
    "Membrana, núcleo y receptor",
    "Cadenas pesadas, livianas y fracción constante",
    "CD4, CD8 y MHC"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué son las citoquinas?",
  opciones: [
    "Moléculas grandes de defensa pasiva",
    "Moléculas proteicas mensajeras del sistema inmune",
    "Hormonas de la médula ósea"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué es un efecto pleiotrópico en citoquinas?",
  opciones: [
    "Una citoquina con múltiples funciones en una célula",
    "Una citoquina con receptores en varios tipos celulares",
    "Una citoquina sin función",
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué significa efecto de redundancia en citoquinas?",
  opciones: [
    "Una citoquina actúa sobre sí misma",
    "Múltiples citoquinas tienen el mismo efecto",
    "Una citoquina sin receptor específico"
  ],
  respuesta: 1
},
{
  pregunta: "¿Cuáles son los niveles de acción de las citoquinas?",
  opciones: [
    "Autocrino, paracrino y endocrino",
    "Nuclear, citoplasmático y extracelular",
    "Mucoso, dérmico y vascular"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué citoquinas se producen en inmunidad adaptativa?",
  opciones: [
    "IL-2, 4, 5 e IFNγ",
    "IgE, IgA, IgG",
    "TNF, GM-CSF, EPO"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuáles son funciones de las citoquinas?",
  opciones: [
    "Activación del sistema digestivo, hormonal y nervioso",
    "Regulación del sistema muscular",
    "Modificación del citoesqueleto, señales al núcleo e inducción de apoptosis"
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué citoquina actúa contra virus?",
  opciones: ["IL-2", "Interferón", "IL-10"],
  respuesta: 1
},
{
  pregunta: "¿Cuáles son citoquinas clave en hematopoyesis?",
  opciones: [
    "IL-3, IL-7, G-CSF, GM-CSF, Eritropoyetina",
    "IL-2, IL-4, IL-5",
    "TNF, IFNγ, IL-1"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuál citoquina es proinflamatoria y estimula secreción de Igs por parte de LsB?",
  opciones: ["IL-6", "IL-4", "IL-10"],
  respuesta: 0
},
{
  pregunta: "¿Qué función tiene la IL-22?",
  opciones: [
    "Estimular la producción de anticuerpos",
    "Defender barreras de superficie e inducir proteínas de fase aguda",
    "Activar linfocitos B de memoria"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué es el efecto de redundancia en citoquinas?",
  opciones: [
    "Varias citoquinas con el mismo efecto biológico",
    "Una citoquina con varios receptores",
    "Repetición de señales por el mismo linfocito"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cómo se clasifican las citoquinas por efecto local?",
  opciones: [
    "Autocrinas y paracrinas",
    "Linfáticas y humorales",
    "Virales y bacterianas"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué interleucina avisa sobre infección viral?",
  opciones: ["IL-6", "IL-2", "Interferón"],
  respuesta: 2
},
{
  pregunta: "¿Cuáles son tres efectos del TNF (Factor de necrosis tumoral)?",
  opciones: [
    "Caquexia, fiebre, síndrome séptico",
    "Dolor, inflamación, necrosis",
    "Mareo, visión borrosa, urticaria"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué puede causar la falta de producción de IL-2?",
  opciones: [
    "Alergia severa",
    "Inmunodeficiencia severa mixta",
    "Linfoma de células T"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué es la tolerancia inmunológica?",
  opciones: [
    "Activación exagerada del sistema inmune",
    "Capacidad de eliminar Ags propios",
    "Pérdida de respuesta a antígenos propios",
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué es la tolerancia central?",
  opciones: [
    "Educación de linfocitos T y B durante su maduración",
    "Respuesta de memoria inmune",
    "Reacción cruzada de antígenos"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es la deleción clonal extratímica?",
  opciones: [
    "Eliminación de linfocitos T autoreactivos fuera del timo",
    "Destrucción de macrófagos en bazo",
    "Muerte celular por calor"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es la miastenia gravis?",
  opciones: [
    "Enfermedad neurodegenerativa",
    "Infección viral del sistema nervioso",
    "Enfermedad autoinmune que causa debilidad muscular"
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué es el síndrome poliendocrino autoinmune?",
  opciones: [
    "Fallo renal múltiple",
    "Síndrome viral congénito",
    "Producción de autoanticuerpos que afectan varios órganos"
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué es la ignorancia clonal?",
  opciones: [
    "Los linfocitos no detectan antígenos propios por barreras anatómicas",
    "Reacción cruzada entre antígenos virales",
    "Respuesta inmune exagerada a MO"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es la tolerancia a dosis bajas de antígeno?",
  opciones: [
    "Resistencia a altas concentraciones de antígeno",
    "Desensibilización por exposición repetida a pequeñas cantidades",
    "Reacción inmediata alérgica"
  ],
  respuesta: 1
},
{
  pregunta: "¿Por qué el embarazo es un tipo de tolerancia inducida?",
  opciones: [
    "Porque el sistema inmune reconoce al feto como extraño y lo elimina",
    "Porque el feto pasa desapercibido por la tolerancia inmunológica de la madre",
    "Porque la placenta elimina todas las células inmunes"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué es la tolerancia oral?",
  opciones: [
    "Capacidad de resistir antígenos de vía respiratoria",
    "Mecanismo de defensa contra bacterias del oído",
    "Respuesta tolerante a antígenos ingeridos, mediada por DCs en el anillo de Waldeyer"
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué células adquieren memoria inmunológica?",
  opciones: [
    "LsB y LsT de memoria",
    "Macrófagos y monocitos",
    "Neutrófilos y eosinófilos"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué molécula inactiva los linfocitos T?",
  opciones: ["CD95", "IL-2", "IgE"],
  respuesta: 0
},
{
  pregunta: "¿Dónde se lleva a cabo la tolerancia central?",
  opciones: ["Bazo y ganglios", "Timo y médula ósea", "Pulmones y piel"],
  respuesta: 1
},
{
  pregunta: "¿Qué ocurre en la ignorancia clonal?",
  opciones: [
    "Los linfocitos se activan ante todos los antígenos",
    "Los antígenos propios están protegidos por barreras anatómicas",
    "Se destruyen linfocitos activados"
  ],
  respuesta: 1
},
{
  pregunta: "¿Cuál es el resultado de la pérdida de tolerancia inmunológica?",
  opciones: [
    "Aumento de memoria inmunológica",
    "Producción de inmunoglobulinas",
    "Enfermedades autoinmunes"
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué se administra en las vacunas antialérgicas?",
  opciones: ["Grandes dosis de antígenos", "Pequeñas cantidades de antígeno", "Adyuvantes virales"],
  respuesta: 1
},
{
  pregunta: "¿Qué es la apoptosis?",
  opciones: [
    "Desintegración del núcleo celular",
    "Fusión de células inmunes",
    "Muerte celular programada"
  ],
  respuesta: 2
},
{
  pregunta: "¿Qué células sufren apoptosis?",
  opciones: [
    "Células con daño genético o que cumplieron su ciclo",
    "Todas las células inmunes",
    "Sólo células nerviosas"
  ],
  respuesta: 0
},
{
  pregunta: "¿Por qué es importante la apoptosis?",
  opciones: [
    "Genera inflamación crónica",
    "Tiene un rol crítico en el desarrollo",
    "Evita la producción de anticuerpos"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué factores evitan la apoptosis?",
  opciones: [
    "Choque térmico, toxinas bacterianas, terapia con radiación",
    "IL-2 y caspasas",
    "Macrófagos y linfocitos"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué factores promueven la apoptosis?",
  opciones: [
    "Genes virales, inhibidores farmacológicos, estrés oxidativo",
    "IL-2 y IL-6",
    "Lactobacilos intestinales"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuáles son las dos vías de muerte celular por apoptosis?",
  opciones: [
    "Nuclear y citoplasmática",
    "Mitocondrial y receptores de muerte",
    "Autofagia y necrosis"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué son las caspasas y cómo se clasifican?",
  opciones: [
    "Lipasas digestivas, 2 tipos",
    "Proteasas que fragmentan ADN, iniciadoras y ejecutoras",
    "Hormonas celulares de defensa"
  ],
  respuesta: 1
},
{
  pregunta: "¿Cuál es el punto irreversible en la apoptosis intracelular?",
  opciones: ["Formación de mitocondrias", "Activación de caspasas", "Expresión de FASL"],
  respuesta: 1
},
{
  pregunta: "¿Cuál es el guardián del genoma humano?",
  opciones: ["CD8", "P53", "CD95"],
  respuesta: 1
},
{
  pregunta: "¿Qué diferencias hay entre apoptosis y necrosis?",
  opciones: [
    "Apoptosis requiere ATP, necrosis no; necrosis causa inflamación",
    "Ambas son procesos inflamatorios",
    "Apoptosis ocurre a 4 °C y necrosis no"
  ],
  respuesta: 0
},
{
  pregunta: "Mencione 2 ligandos de muerte en apoptosis:",
  opciones: ["FASL y DIABLO", "CD4 y CD8", "IgA y IgM"],
  respuesta: 0
},
{
  pregunta: "¿Qué células producen la netosis?",
  opciones: ["Neutrófilos (PMNs)", "Linfocitos B", "Células NK"],
  respuesta: 0
},
{
  pregunta: "¿Cómo se llama el guardián del genoma humano?",
  opciones: ["P53", "IgE", "TNF"],
  respuesta: 0
},
{
  pregunta: "¿Cuál es la sustancia clave en la apoptosis mitocondrial?",
  opciones: ["Citocromo C", "CD95", "IL-2"],
  respuesta: 0
},
{
  pregunta: "¿Cuál es la inmunoglobulina más presente en el cuerpo?",
  opciones: ["IgM", "IgG", "IgE"],
  respuesta: 1
},
{
  pregunta: "¿Cuál es el método más usado para medir anticuerpos?",
  opciones: ["Electroforesis", "PCR", "Western blot"],
  respuesta: 0
},
{
  pregunta: "¿Para qué sirve el centrifugado en inmunología?",
  opciones: [
    "Separar linfocitos de otras células",
    "Mezclar soluciones",
    "Disolver proteínas"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué célula se afecta más en el VIH?",
  opciones: ["LsT CD4", "LsB", "Macrófagos"],
  respuesta: 0
},
{
  pregunta: "¿En qué consiste el método ELISA?",
  opciones: [
    "Inmunoensayo para detectar antígenos o anticuerpos",
    "Técnica de separación celular",
    "Evaluación de ADN mitocondrial"
  ],
  respuesta: 0
},
{
  pregunta: "Menciona una técnica de quimiotaxis:",
  opciones: ["Cámara de Boyden", "Western blot", "PCR"],
  respuesta: 0
},
{
  pregunta: "¿Por qué ya no se usa el radioinmunoanálisis?",
  opciones: [
    "Alto costo",
    "Contaminación radioactiva",
    "Inexactitud del resultado"
  ],
  respuesta: 1
},
{
  pregunta: "¿Diferencia entre prueba de Coombs directa e indirecta?",
  opciones: [
    "Directa usa glóbulos rojos; indirecta usa el plasma del paciente",
    "Indirecta es más precisa",
    "Directa solo mide anticuerpos IgA"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué describe el ELISA directo?",
  opciones: [
    "Antígeno, anticuerpo, antígeno secundario y sustrato",
    "Medición de ADN viral",
    "Evaluación de PCR"
  ],
  respuesta: 0
},
{
  pregunta: "Menciona una prueba de detección de alergias:",
  opciones: ["Intradermorreacción", "Western blot", "ELISA indirecto"],
  respuesta: 0
},
{
  pregunta: "¿Qué es la inmunidad órgano específica?",
  opciones: [
    "Sistema inmune con características adaptadas por órgano",
    "Respuesta generalizada a todos los órganos",
    "Función exclusiva del sistema nervioso"
  ],
  respuesta: 0
},
{
  pregunta: "Menciona 2 mecanismos innatos de defensa en la piel:",
  opciones: ["pH y melanocitos", "IgG e IgA", "CD4 y CD8"],
  respuesta: 0
},
{
  pregunta: "Menciona 2 mecanismos adquiridos de defensa en la piel:",
  opciones: ["SALT y células dendríticas", "IgE y macrófagos", "Melanocitos y neutrófilos"],
  respuesta: 0
},
{
  pregunta: "¿Qué es el pénfigo?",
  opciones: [
    "Enfermedad con ampollas por pérdida de unión entre queratinocitos",
    "Infección viral",
    "Alergia respiratoria"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué forma el manto ácido protector de la piel?",
  opciones: [
    "Microbioma y piel",
    "Sudor y melanocitos",
    "IgE y macrófagos"
  ],
  respuesta: 0
},
{
  pregunta: "Mecanismo innato gastrointestinal:",
  opciones: ["Saliva y acidez gástrica", "SALT y células dendríticas", "IgG y linfocitos B"],
  respuesta: 0
},
{
  pregunta: "Mecanismo adquirido gastrointestinal:",
  opciones: ["Quimiocinas y anticuerpos", "pH ácido y queratinocitos", "Citocromo C y caspasas"],
  respuesta: 0
},
{
  pregunta: "Neumocito tipo I y II:",
  opciones: [
    "Tipo I: difunde gases; Tipo II: secreta surfactante y presenta Ag",
    "Ambos producen IgA",
    "Tipo II actúa en coagulación"
  ],
  respuesta: 0
},
{
  pregunta: "Enfermedad autoinmune más frecuente en el riñón:",
  opciones: ["Glomerulonefritis", "Pénfigo", "Miastenia gravis"],
  respuesta: 0
},
{
  pregunta: "¿Por qué el ojo es un órgano inmuno privilegiado?",
  opciones: [
    "Tiene barreras que lo aíslan del sistema inmune para proteger su estructura",
    "Produce IgE de forma natural",
    "Está constantemente expuesto al aire"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué molécula se asocia con osteoporosis?",
  opciones: ["OSCAR", "CD4", "P53"],
  respuesta: 0
},
{
  pregunta: "¿Cómo se llaman las células dendríticas de la piel?",
  opciones: ["Células de Langerhans", "Células de Kupffer", "Células de Schwann"],
  respuesta: 0
},
{
  pregunta: "Menciona 2 mecanismos innatos de inmunidad en la piel:",
  opciones: ["pH y melanocitos", "IgA y IgE", "Neutrófilos y caspasas"],
  respuesta: 0
},
{
  pregunta: "¿Qué células inmunes hay en los alvéolos?",
  opciones: ["Macrófagos y linfocitos T", "Eosinófilos y neutrófilos", "Células NK y caspasas"],
  respuesta: 0
},
{
  pregunta: "¿Qué ocurre en el pénfigo a nivel inmunológico?",
  opciones: [
    "El sistema inmune ataca proteínas que unen queratinocitos",
    "Hay producción de anticuerpos IgE contra virus",
    "Se destruyen fibras musculares",
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué hormona está elevada durante el embarazo?",
  opciones: ["HCG", "FSH", "TSH"],
  respuesta: 0
},
{
  pregunta: "¿Cuál es la función de la flora bacteriana en el tracto genital femenino?",
  opciones: [
    "Proteger frente a patógenos mediante el pH ácido",
    "Inducir producción de caspasas",
    "Activar receptores de glucosa"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué células inmunes predominan en el cuello uterino?",
  opciones: ["LsT, CD4, CD8, células plasmáticas e IgA/IgG", "Células gliales", "Neutrófilos y eosinófilos"],
  respuesta: 0
},
{
  pregunta: "¿Por qué el testículo es un órgano inmuno privilegiado?",
  opciones: [
    "Posee una barrera hematotesticular que limita acceso del sistema inmune",
    "No hay células inmunes en el testículo",
    "Produce anticuerpos de forma autónoma"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué pasa si se pierde la continuidad de la barrera hematotesticular?",
  opciones: [
    "Puede generar esterilidad",
    "Aumenta la testosterona",
    "Incrementa la inmunidad"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué inmunoglobulina atraviesa la placenta?",
  opciones: ["IgG", "IgA", "IgM"],
  respuesta: 0
},
{
  pregunta: "¿Cómo adquiere microbiota el recién nacido?",
  opciones: [
    "Durante el alumbramiento según la vía de parto",
    "A través de la leche materna exclusivamente",
    "Por contacto con oxígeno"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué flora bacteriana adquiere un bebé por parto vaginal?",
  opciones: ["Lactobacilos", "Estafilococos", "Escherichia coli"],
  respuesta: 0
},
{
  pregunta: "¿Qué flora bacteriana predomina tras parto por cesárea?",
  opciones: ["Estafilococos", "Lactobacilos", "Clostridium"],
  respuesta: 0
},
{
  pregunta: "¿Cuál es una diferencia entre calostro y leche materna?",
  opciones: [
    "Calostro contiene más leucocitos y lactoferrina",
    "Leche materna tiene más caspasas",
    "Calostro es producido por el padre"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué proporciona el calostro al recién nacido?",
  opciones: [
    "Anticuerpos y células inmunes",
    "Vitaminas A y D",
    "Glucosa y minerales"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué hormona reduce la respuesta inmune durante el embarazo?",
  opciones: ["Estrógeno y progesterona", "Testosterona", "TSH"],
  respuesta: 0
},
{
  pregunta: "Menciona dos microorganismos que afectan inmunidad reproductiva:",
  opciones: ["Neisseria gonorrhoeae y VIH", "VPH y rotavirus", "Clostridium y lactobacilos"],
  respuesta: 0
},
{
  pregunta: "¿Qué inmunoglobulinas se transfieren al feto durante el 3er trimestre?",
  opciones: ["IgE e IgG", "IgA e IgM", "IgM e IgE"],
  respuesta: 0
},
{
  pregunta: "¿Cuál es la función del pH vaginal ácido?",
  opciones: [
    "Evitar proliferación de patógenos y proteger mucosa",
    "Regular el ciclo ovárico",
    "Aumentar fertilidad"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es inmunización?",
  opciones: [
    "Inducción de inmunidad mediante agente biológico",
    "Respuesta inflamatoria a toxinas",
    "Generación de anticuerpos sin contacto previo"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es una vacuna?",
  opciones: [
    "Un preparado de proteínas o MO atenuados para inducir inmunización",
    "Un antibiótico natural",
    "Una hormona sintética"
  ],
  respuesta: 0
},
{
  pregunta: "¿Los pacientes padecen la enfermedad contra la que va la vacuna?",
  opciones: [
    "No, las vacunas enseñan al sistema inmune sin causar la enfermedad",
    "Sí, siempre presentan síntomas leves",
    "Solo si tienen predisposición genética"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es inmunidad efectiva?",
  opciones: [
    "Lograr memoria inmunológica contra una enfermedad",
    "Generar fiebre ante una infección",
    "Estimular anticuerpos pasivos"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cómo se clasifica la inmunidad que otorgan las vacunas?",
  opciones: [
    "Inmunidad adquirida activa artificial",
    "Inmunidad innata pasiva",
    "Inmunidad adquirida pasiva natural"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es un toxoide?",
  opciones: [
    "Toxina bacteriana modificada sin toxicidad",
    "Virus atenuado",
    "Receptor de superficie"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué es la cadena de frío en vacunas?",
  opciones: [
    "Proceso de conservación a 2°C–8°C para mantener eficacia",
    "Cadena de suministro hospitalario",
    "Red de distribución eléctrica para refrigeradores"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuál NO es una característica de la vacuna ideal?",
  opciones: [
    "Fácil producción, efectiva, inmunidad persistente",
    "Produce fiebre alta para generar inmunidad",
    "Debe mimetizar infección natural sin causar enfermedad"
  ],
  respuesta: 1
},
{
  pregunta: "¿Qué vacuna contra poliomielitis se administra por vía oral?",
  opciones: ["Sabin", "Salk", "BCG"],
  respuesta: 0
},
{
  pregunta: "¿Qué protege la vacuna DPT?",
  opciones: [
    "Difteria, tos ferina y tétanos",
    "Sarampión, rubéola y hepatitis B",
    "Tuberculosis, polio y fiebre amarilla"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué cubre la vacuna hexavalente?",
  opciones: [
    "Difteria, tos ferina, tétanos, hepatitis B, Hib y polio",
    "Hepatitis A, B y C, difteria y VIH",
    "Sarampión, rubeola y parotiditis"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué cubre la vacuna MMR (triple viral)?",
  opciones: [
    "Sarampión, rubéola y parotiditis",
    "Difteria, tétanos y poliomielitis",
    "Hepatitis B, Hib y sarampión"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuáles son 3 características clave de una vacuna ideal?",
  opciones: [
    "Económica, efectiva, en dosis única",
    "Dolorosa, lenta y costosa",
    "De aplicación mensual, con múltiples efectos adversos"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuál es la diferencia entre toxoide y antitoxina?",
  opciones: [
    "Toxoide: toxina debilitada / Antitoxina: antídoto contra la toxina",
    "Ambas son anticuerpos",
    "Toxoide: anticuerpo / Antitoxina: proteína plasmática"
  ],
  respuesta: 0
},
{
  pregunta: "¿Cuál vacuna contra polio es oral y cuál parenteral?",
  opciones: [
    "Sabin oral, Salk parenteral",
    "Salk oral, Sabin parenteral",
    "Ambas son orales"
  ],
  respuesta: 0
},
{
  pregunta: "¿Qué vacuna de ADN recombinante usa levaduras?",
  opciones: ["Vacuna contra hepatitis B", "Vacuna contra VPH", "Vacuna contra influenza"],
  respuesta: 0
},
{
  pregunta: "¿Qué enfermedades previene la vacuna MMR?",
  opciones: [
    "Sarampión, parotiditis y rubéola",
    "Hepatitis B, difteria y sarampión",
    "Tétanos, tos ferina y varicela"
  ],
  respuesta: 0
}

 
    ];

    const contenedor = document.getElementById("quiz-container");

    preguntas.forEach((q, index) => {
    const div = document.createElement("div");
    div.className = "question-container";

    const preguntaEl = document.createElement("p");
    preguntaEl.textContent = `${index + 1}. ${q.pregunta}`;
    div.appendChild(preguntaEl);

    q.opciones.forEach((opcion, i) => {
      const btn = document.createElement("button");
      btn.textContent = opcion;
      btn.onclick = () => {
        if (i === q.respuesta) {
          btn.classList.add("correct");
          btn.textContent += " ✅ ¡Correcto!";
          // Desactiva todos los botones cuando acierta
          const botones = div.querySelectorAll("button");
          botones.forEach(b => b.disabled = true);
        } else {
          btn.classList.add("incorrect");
          btn.textContent += " ❌ Intenta de nuevo.";
          btn.disabled = true; // Solo desactiva este botón incorrecto
        }
      };
      div.appendChild(btn);
    });

    contenedor.appendChild(div);
  });
</script>
