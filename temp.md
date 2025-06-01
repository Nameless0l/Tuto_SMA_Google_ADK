```mermaid
---
config:
  theme: redux
---
**sequenceDiagram**
    participant U as 👨‍🌾 Agriculteur
    participant UI as 🌐 Interface Web
    participant AP as 🤖 Agent Principal
    participant AE as 💰 Agent Économique
    participant MA as 📈 Market API
    participant AC as 🌱 Agent Cultures
    participant AM as 🌤️ Agent Météo
    participant G as 🧠 Gemini LLM

    U->>UI: "Quel culture sera<br/>plus rentable cette saison ?"
    UI->>AP: Requête analyse économique
    
    Note over AP: Analyse multi-critères<br/>nécessaire
    
    par Collecte données marché
        AP->>AE: Analyse rentabilité cultures
        AE->>MA: Prix actuels + tendances
        MA-->>AE: Données marché complètes
    and Données techniques
        AP->>AC: Cultures adaptées région
        AC-->>AP: Liste cultures possibles<br/>+ rendements moyens
    and Données météo
        AP->>AM: Prévisions saisonnières
        AM-->>AP: Conditions climatiques<br/>prévues
    end
    
    AE->>G: Analyse comparative<br/>rentabilité par culture
    G-->>AE: Calculs ROI, risques,<br/>marges bénéficiaires
    
    Note over AE,AC: Corrélation données<br/>marché + techniques
    
    AE->>AC: Partage données prix<br/>pour optimisation
    AC->>AE: Retour rendements<br/>par culture
    
    AE->>G: Synthèse finale<br/>multi-critères
    G-->>AE: Recommandations classées<br/>par rentabilité + risque
    
    AE-->>AP: Top 3 cultures rentables:<br/>1. Maïs (ROI: 145%)<br/>2. Haricots (ROI: 120%)<br/>3. Tomates (ROI: 110%)
    
    AP->>G: Validation cohérence<br/>avec contraintes locales
    G-->>AP: Recommandation finale<br/>personnalisée
    
    AP-->>UI: Analyse économique complète<br/>+ projections financières
    UI-->>U: "Maïs recommandé:<br/>Investissement: 500,000 FCFA<br/>Retour prévu: 725,000 FCFA<br/>Risque: Faible"
```