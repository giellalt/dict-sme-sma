1. sjekke entryer med flere oversettinger. 
Start med disse:
varas
eana
guovlu
orohat
mohkki
oahppu
bivdit
coggat
mannat
orrut
sorbmet


Kommando for å se bare entryer med flere enn en oversetting, som ei liste med sme-ord pluss sma-oversettinger, inkludert <re>:
sed  's/<e/¢<e/' src/x_smesma.xml | tr '\n' '€' | tr '¢' '\n' | grep '<mg>.*<mg>' | tr '€' '\n' |sed 's/<l /¢<l /' | sed 's/<t /¢<t /g' |egrep '(¢|<re>)' |tr '<' '>' | cut -d '>' -f1,3 |less

Liste over flere ord i inc/severaltransl_list.txt


* Stryke oversettinger som er overflødige, eller er ment for helt spesielle tilfeller  (stryk tilsvarende ordpar fra smasme/src/x_smasme.xml)
* og/eller legge til eksempel eller <re> (innholdet i re skal være på sme, fordi det er ment for den som ikke kan sma)

   <e>
      <lg>
         <l pos="N">diibmu</l>
      </lg>
      <mg>
         <tg xml:lang="sma">
         <re>áigi</re>
            <t pos="N">tæjmoe</t>
         </tg>
      </mg>
      <mg>
         <tg xml:lang="sma">
         <re>neavvu</re>            
         <t pos="N">tsåahka</t>
         </tg>
      </mg>
   </e>
   
 
   <e xpos="obs">
      <lg>
         <l pos="A" spec="Sem_Dummytag.Sg.Nom">vejolaš</l>
      </lg>
      <mg>
         <tg xml:lang="sma">
            <t pos="V">gåaradidh</t>
            <xg>
               <x>Lea vejolaš addit stipeandda joatkkaskuvlla ohppiide...</x>
               <xt>Gåarede stipeendem vedtedh jåarhkeskuvlen learoehkidie...</xt>
            </xg>
            <xg>
               <x>Ja danne ii leat ge vejolaš gávnnahit sámegielagiid logu dáinna vugiin.</x>
               <xt>Jïh dannasinie ij vielie gåaredh daejredh man jïjnjh almetjh mah naemhtie saemiestieh.</xt>
            </xg>
         </tg>
      </mg>
      <mg>
         <tg xml:lang="sma">
            <t pos="A" spec="Attr">nuepies</t>
            <xg>
               <x>... jus gielaid ii leat vejolaš geavahit árgabeaivvis.</x>
               <xt>... jis ij leah nuepie gïelem fïerhtenbeajjetjegïeline utnedh.</xt>
            </xg>
         </tg>
      </mg>
      <mg>
         <tg xml:lang="sma">
            <t pos="V">buektiehtidh</t>
            <xg>
               <x>Ii leat dássážii leamaš vejolaš juolludit eambbo go 5-600.000 ruvnno...</x>
               <xt>Ij leah buektiehtamme vielie goh 5-600.000 kråvnah vedtedh...</xt>
            </xg>
         </tg>
      </mg>
   </e>
  

* Endre rekkefølge slik at den mest generelle mg kommer først (hvis det virker fornuftig)

Lista oppdateres med denne:

sed 's/<e/¢<e/' src/x_smesma.xml | tr '\n' ' ' | tr '¢' '\n' | grep '<mg>.*<mg>' |tr '<' '>' | cut -d '>' -f7 > inc/severaltransl_list.txt 


2. sjekke entryer merka med  xpos="obs" (f.eks. eksemplene)

