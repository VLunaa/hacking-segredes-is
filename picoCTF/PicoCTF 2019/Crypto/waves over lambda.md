## Descripción

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 13758`.

## Solución
- Otra vez tenemos un mensaje encriptado, usé la herramienta DCODE para decodificarlo.

```
┌──(kali㉿kali)-[~/Downloads]

└─$ nc jupiter.challenges.picoctf.org 13758

-------------------------------------------------------------------------------

rzgbvkui teve ci wzdv ohkb - ovexdegrw_ci_r_zmev_hksynk_ngmuovukwd

-------------------------------------------------------------------------------

yeuqeeg di uteve qki, ki c tkme khveknw ikcn izseqteve, ute yzgn zo ute iek. yeicnei tzhncgb zdv tekvui uzbeutev utvzdbt hzgb levczni zo ielkvkuczg, cu tkn ute eooeru zo skacgb di uzhevkgu zo ekrt zutev'i wkvgikgn emeg rzgmcruczgi. ute hkqwevute yeiu zo zhn oehhzqitkn, yerkdie zo tci skgw wekvi kgn skgw mcvudei, ute zghw rditczg zg nera, kgn qki hwcgb zg ute zghw vdb. ute krrzdgukgu tkn yvzdbtu zdu khveknw k yzj zo nzscgzei, kgn qki uzwcgb kvrtcuerudvkhhw qcut ute yzgei. skvhzq iku rvzii-hebben vcbtu kou, hekgcgb kbkcgiu ute scppeg-skiu. te tkn idgaeg rteeai, k wehhzq rzslhejczg, k iuvkcbtu ykra, kg kireucr kileru, kgn, qcut tci kvsi nvzllen, ute lkhsi zo tkgni zduqkvni, veiesyhen kg cnzh. ute ncveruzv, ikuciocen ute kgrtzv tkn bzzn tzhn, skne tci qkw kou kgn iku nzqg kszgbiu di. qe ejrtkgben k oeq qzvni hkpchw. kouevqkvni uteve qki ichegre zg yzkvn ute wkrtu. ozv izse vekizg zv zutev qe ncn gzu yebcg utku bkse zo nzscgzei. qe oehu sencukucme, kgn ocu ozv gzutcgb ydu lhkrcn iukvcgb. ute nkw qki egncgb cg k ievegcuw zo iuchh kgn ejxdcicue yvchhckgre. ute qkuev itzge lkrcocrkhhw; ute iaw, qcutzdu k ilera, qki k yegcbg cssegicuw zo dgiukcgen hcbtu; ute mevw sciu zg ute eiiej skvit qki hcae k bkdpw kgn vknckgu okyvcr, tdgb ovzs ute qzznen vciei cghkgn, kgn nvklcgb ute hzq itzvei cg nckltkgzdi ozhni. zghw ute bhzzs uz ute qeiu, yvzzncgb zmev ute dllev vekrtei, yerkse szve izsyve emevw scgdue, ki co kgbeven yw ute kllvzkrt zo ute idg.

```

Mensaje desencriptado:

```
------------------------------------------------------------------------------- CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_DNVTFRTAYU ------------------------------------------------------------------------------- HAVING HAD SOME TIME AT MY DISPOSAL WHEN IN LONDON, I HAD VISITED THE BRITISH MUSEUM, AND MADE SEARCH AMONG THE BOOKS AND MAPS IN THE LIBRARY REGARDING TRANSYLVANIA; IT HAD STRUCK ME THAT SOME FOREKNOWLEDGE OF THE COUNTRY COULD HARDLY FAIL TO HAVE SOME IMPORTANCE IN DEALING WITH A NOBLEMAN OF THAT COUNTRY. I FIND THAT THE DISTRICT HE NAMED IS IN THE EXTREME EAST OF THE COUNTRY, JUST ON THE BORDERS OF THREE STATES, TRANSYLVANIA, MOLDAVIA AND BUKOVINA, IN THE MIDST OF THE CARPATHIAN MOUNTAINS; ONE OF THE WILDEST AND LEAST KNOWN PORTIONS OF EUROPE. I WAS NOT ABLE TO LIGHT ON ANY MAP OR WORK GIVING THE EXACT LOCALITY OF THE CASTLE DRACULA, AS THERE ARE NO MAPS OF THIS COUNTRY AS YET TO COMPARE WITH OUR OWN ORDNANCE SURVEY MAPS; BUT I FOUND THAT BISTRITZ, THE POST TOWN NAMED BY COUNT DRACULA, IS A FAIRLY WELL-KNOWN PLACE. I SHALL ENTER HERE SOME OF MY NOTES, AS THEY MAY REFRESH MY MEMORY WHEN I TALK OVER MY TRAVELS WITH MINA.

```

La bandera no está en el formato normal, solamente hay que pegarla.

FREQUENCY_IS_C_OVER_LAMBDA_DNVTFRTAYU