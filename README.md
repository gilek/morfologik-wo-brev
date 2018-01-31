# morfologik-wo-brev
Korzystając z [Morfologika](https://github.com/morfologik/morfologik-stemming) jako stemmera Solr należy być świadomym, że w swoim słowniku zawiera również skróty. Niesie to ze sobą efekt, który nie zawsze jest pożądany. Dla przykładu, wyszukując frazę „office pl” otrzymujemy tokeny [office, pl, plac].

Repozytorium zawiera przerobiony słownik morfologika pozbawiony skrótów. Więcej na temat jego tworzenia można przeczytać na [moim blogu](http://blog.gilek.net/morfologik-usuwanie-skrotow-ze-slownika/).

## Instalacja
1. Pliki *.dist oraz *.info przenosimy do katalogu `<INSTALL_DIR>/solr/server/resources`

2. Definicja filtra w analzatorze wygląda następująco:
```xml
<filter class="solr.MorfologikFilterFactory" dictionary="polish-wo-brev.dict" />
```
