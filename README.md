# Projets de Robotique — IUT Paris-Saclay

Projets de robotique compétitive et SAE embarqué réalisés à l'IUT de Cachan (Université Paris-Saclay).

---

## Coupe de France de Robotique 2023 — *The Cherry on the Cake*

Conception complète d'un robot autonome capable d'assembler des gâteaux, déposer des cerises
et marquer des points de façon autonome en 100 secondes de match.

**Équipe :** Thomas VELARD, Eaklim HOUR, Julien TERRIER, Kiritheepan ROBINSAN, Rémi WAN, Alpha DIALLO

### Architecture du système

```
Raspberry Pi 4  ──── Lidar R2000 (détection des adversaires)
      │
   Bus CAN
 ┌────┼─────────────┬──────────────┐
 │                  │              │
Carte IHM      Carte Moteur   Carte Herkulex
(Disco F469)   (STM32 F303K8) (STM32 F303K8)
Écran tactile  Odométrie       Servos Herkulex
Bluetooth      Asservissement  Aspiration cerises
Carte SD       PID position    Barillet
```

### Fonctionnalités

- Déplacement asservi par **odométrie** (encodeurs magnétiques en quadrature)
- Assemblage de gâteaux légendaires (3 couches de couleurs dans un ordre précis)
- Aspiration et dépôt de cerises via turbine + barillet contrôlés par servos Herkulex
- Communication inter-robots et avec le panier par **Bluetooth**
- Détection et évitement d'obstacles par **Lidar R2000**
- Interface tactile (Disco F469NI) pour la sélection de stratégie via éditeur graphique (QT)

### Stack technique

```
MCU       : STM32F303K8 · STM32F469I Discovery · Raspberry Pi 4
Protocole : Bus CAN · UART (Herkulex) · Bluetooth · SPI
Logiciel  : C/C++ · Mbed · éditeur de stratégie QT
CAO       : Altium Designer (PCB) · SolidWorks (mécanique)
Outils    : KeilStudio · CubeMX
```

---

## SAE Robot — Gamel Trophy (suiveur de ligne autonome)

Conception d'une carte capteur de A à Z : schéma, routage sous Altium, gravure chimique du PCB,
soudage des composants et campagne de tests.

```
Étapes : Cahier des charges → Altium → Gravure PCB → Soudage → Tests
Tests  : Continuité · Isolation · Statique · Fonctionnel · Programme
```

---

## Documents

| Fichier | Description |
|---------|-------------|
| `Rapport_Coupe_de_France_Robotique.pdf` | Rapport SAE S4 complet (60 pages) |
| `Rapport_Coupe_de_France_Robotique_CORRIGE.docx` | Source Word corrigée du rapport |
| `robot_SAE_portfolio.pdf` | Portfolio du robot SAE (carte capteur, PCB, tests) |
| `Carte_herkulex_WPT.pdf` | Carte servos Herkulex + infographie WPT (transfert d'énergie sans fil) |

---

ROBINSAN Kiritheepan — Étudiant ingénieur à l'ENSEA
