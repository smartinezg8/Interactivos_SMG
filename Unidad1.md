
# Sesión mnarte 21 de julio

## Ensayo 1

Martes alcancé a realizar esta prueba

``` js
note("48 51 53, 65 78, 34").sound("piano")
note("24 20 15 31 25 15").sound("gm_electric_guitar_muted")
note("45 54 29 31 32").sound("gm_acoustic_bass") 
note("46 65, 58 54 55 51").sound("gm_voice_oohs")

let drum = stack(
  s("oh").beat("0,5,10",16), 
  s("hh").beat("3,7,11,14",16),
  s("cp").beat("0,2,4,6,8,11,13,15",16),
  s("bd").beat("2, 5, 7, 8",16),
).bank("RhythmAce")
//$:drum

sound("bd cp*3 hh oh*5")
sound("bd*2, hh*2 [hh bd hh]")

note("<[24 53]*3 [36 55]*3 [26 21]*3 [22]/2>")
.sound("gm_acoustic_bass")


setcpm(64)
n("<5 1>, 0 6 3 <[3,5] [4,8] [6,9]>")
.scale("<A2:minor:pentatonic F:major:pentatonic D:dorian>/6")
.sound("gm_acoustic_bass") 
```


## Ejercicio 1
``` js
setcpm(64)
let harmony = note("<5 1>, 0 6 3 <[3,5] [4,8] [6,9]>")
.scale("<A2:minor:pentatonic F:major:pentatonic D:dorian>/6")
.sound("gm_acoustic_bass")
.gain(0.7)
.room(2);
$: harmony

let melody = note("36 67 55 <[45] [48, 55]>")
  .sound("gm_voice_oohs")
  .gain(0.6);
$: melody

let percusion = sound("- sh@5 - sh, [- lt]*2")
  .bank("RolandTR707")
  .gain(0.2);
$: percusion

let drum1 = stack(
 sound("bd*2, hh*2 [hh bd hh]"),
 sound("bd cp*3 hh oh*1")
).bank("RolandTR707")
 .gain(0.3)
 .slow(3);
$:drum1
```
