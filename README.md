<a href="https://www.buymeacoffee.com/uMhxJCzPS" target="_blank"><img
src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png"
alt="Buy Me A Coffee" style="height: 41px !important;width: 174px
!important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5)
!important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5)
!important;" ></a>

## App configuration

```yaml
Piscine:
  class: FiltrationPiscine
  module: filtration_piscine
# Capteurs
  temperature_eau: sensor.temp_piscine
# Selection du mode fonctionnement de la filtration
  mode_de_fonctionnement: input_select.mode_fonctionnement_piscine
# Heure pivot autour de laquelle le temps de filtration est réparti (50/50)
  h_pivot: input_datetime.heure_pivot_pisc
# Heure de début de filtration en hiver
  h_debut_hiver: input_datetime.heure_ma_pump_pisc_hiv
# Durée de la filtration en hiver
  duree_hiver: input_number.duree_filtration_max_mode_hiver
# Coefficient du temps de filtration entre 60 et 140%
  coef: input_number.filtration_coeff_abaque
# Validation de mode de calcul avec Abaque sinon c'est la méthode classique (T°/2)
  mode_calcul: input_boolean.calcul_mode_abaque
# Temps circulation de l'eau avant prise en compte mesure température
# dans le cas où la mesure de température de l'eau se trouve sur le circuit de pompage
  tempo_eau: input_number.tempo_circulation_eau
# Memoire de la temperature de l'eau avant arret
  mem_temp: input_number.mem_temp_piscine
# Arret forcé filtration- Bloque la filtration si = on
  #arret_force: input_boolean.piscine_arret_force # à utiliser par défaut
  arret_force: input_boolean.piscine_arret_force
# Ajouté le 30 mai 2022
  # Durée de la filtration en ete
  duree_filtration_ete: input_number.duree_filtration_ete

# Actionneurs
  # Switch de commande de la pompe
  cde_pompe: switch.ppe_filtration
  # Affichage dans HA des heures de filtration
  periode_filtration: input_text.piscine_periode_filtration
```

key | optional | type | default | description
-- | -- | -- | -- | --
`module` | False | string | | `nightmode`
`class` | False | string | | `NightMode`
`temperature_eau:` | True | string || Sensor temperature de l'eau.
`night_brighness` | True | number from 1-255 || The default brightness of the lights listed above during night mode.

