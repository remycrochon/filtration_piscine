# Filtration_piscine
[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)


_Gestion du temps de filtration d'une piscine._

## Installation

This app is best installed using
[HACS](https://github.com/custom-components/hacs), so that you can easily track
and download updates.

Alternatively, you can download the `nightmode` directory from inside the `apps` directory here to your
local `apps` directory, then add the configuration to enable the `filtration_piscine`
module.

## App configuration

```yaml
Piscine:
  class: FiltrationPiscine
  module: filtration_piscine
  temperature_eau: sensor.temp_piscine
  mode_de_fonctionnement: input_select.mode_fonctionnement_piscine
  h_pivot: input_datetime.heure_pivot_pisc
  h_debut_hiver: input_datetime.heure_ma_pump_pisc_hiv
  duree_hiver: input_number.duree_filtration_max_mode_hiver
  coef: input_number.filtration_coeff_abaque
  mode_calcul: input_boolean.calcul_mode_abaque
  tempo_eau: input_number.tempo_circulation_eau
  mem_temp: input_number.mem_temp_piscine
  arret_force: input_boolean.piscine_arret_force
  duree_filtration_ete: input_number.duree_filtration_ete
  periode_filtration: input_text.piscine_periode_filtration
```

key | optional | type | default | description
-- | -- | -- | -- | --
`module` | False | string | | `nightmode`
`class` | False | string | | `NightMode`
`temperature_eau:` | False | string | sensor.temp_piscine | Mesure de la temperature de l'eau.
`mode_de_fonctionnementt` | False | string | input_select.mode_fonctionnement_piscine | Selection du mode fonctionnement de la filtration.
`h_pivot` | False | string | input_datetime.heure_pivot_pisc | Heure pivot autour de laquelle le temps de filtration est réparti (50/50).
`h_debut_hiver` | False | string | input_datetime.heure_ma_pump_pisc_hiv | Heure de début de filtration en hiver.
`duree_hiver` | False | string | input_number.duree_filtration_max_mode_hiver | Durée de la filtration en hiver.
`coef` | False | string | input_number.filtration_coeff_abaque | Coefficient du temps de filtration entre 60 et 140%
`mode_calcul` | False | string | input_boolean.calcul_mode_abaque | Validation de mode de calcul avec Abaque sinon c'est la méthode classique (T°/2)
`tempo_eau` | False | string | input_number.tempo_circulation_eau | # Temps circulation de l'eau avant prise en compte mesure température dans le cas où la mesure de température de l'eau se trouve sur le circuit de pompage.
`mem_temp` | False | string | input_number.mem_temp_piscine |  Memoire de la temperature de l'eau avant arret.
`arret_force` | False | string | input_boolean.piscine_arret_force | Arret forcé filtration- Bloque la filtration si = on.
`duree_filtration_ete` | False | string | input_number.duree_filtration_ete | # Affiche la durée de la filtration en ete.
`cde_pompe` | False | string | switch.ppe_filtration | Switch de commande de la pompe.
`periode_filtration` | False | string | input_text.piscine_periode_filtration | Affichage dans HA des heures de filtration.

