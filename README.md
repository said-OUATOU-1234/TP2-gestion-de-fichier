# TP2-gestion-de-fichier
console.log('tp2:gestion des notes');

const etudient = [
    {id:1, nom:'Amine', note:16},
    {id:2, nom:'Youssef', note:8},
    {id:3, nom:'Salam', note:14},
    {id:4, nom:'omar', note:12},
];

console.log(etudient);
console.log('permier:', etudient[0].nom);
console.log('Effectif:', etudient.length);

// 1. validation
function noteValid(note){
    return Number.isFinite(note) && note >= 0 && note <= 20;
}
console.log(noteValid(16));
console.log(noteValid(25));

// 2. moyenne
function moyenne(notes){
    if (notes.length === 0) return null;
    const total = notes.reduce(
        (somme, note) => somme + note, 0
    );
    return total / notes.length;
}

const notes = etudient.map((e) => e.note);
console.log('moyenne:', moyenne(notes));

// 3. admis
const admis = etudient.filter(
    (e) => e.note >= 10
);
console.log('admis:', admis.length);
console.log(admis);

// 4. lignes + decision
const lignes = etudient.map((e) => {
    const decision = e.note >= 10 ? 'admis' : 'ajourne';
    return `${e.nom} - ${e.note}/20 - ${decision}`;
});

for(const ligne of lignes){
    console.log(ligne);
}
