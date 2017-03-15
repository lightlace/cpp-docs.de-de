---
title: "C++- Typsystem (Modern C++)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# C++- Typsystem (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das *Typ*\-Konzept ist in C\+\+ sehr wichtig.  Jede Variable, jedes Funktionsargument und jeder Rückgabewert muss über einen Typ verfügen, um kompiliert werden zu können.  Außerdem wird jedem Ausdruck \(einschließlich Literalwerten\) vom Compiler implizit ein Typ angegeben, bevor der Ausdruck ausgewertet wird.  Einige Beispiele für Typen sind unter anderem `int` zum Speichern ganzzahliger Werte, `double` zum Speichern von Gleitkommawerten \(auch als *skalare*\-Datentypen bekannt\) oder die Standardbibliotheksklasse [std::basic\_string](../standard-library/basic-string-class.md) zum Speichern von Text.  Sie können auch einen eigenen Typ erstellen, indem Sie eine `class` oder ein `struct` definieren.  Der Typ gibt den Speicher an, der für die Variable \(oder das Ausdrucksergebnis\) zugeordnet ist, die Wertarten, die in dieser Variablen gespeichert werden können, wie diese Werte \(als Bitmuster\) interpretiert werden, und die Vorgänge, die darauf ausgeführt werden können.  In diesem Artikel ist eine informelle Übersicht der Hauptfunktionen des C\+\+\-Typsystems enthalten.  
  
## Terminologie  
 **Variable**: der symbolische Name einer Datenmenge. Der Name kann verwendet werden, um auf die Daten, auf die er verweist, im gesamten Codebereich, in dem der Name definiert wird, zuzugreifen.  In C\+\+ wird "Variable" im Allgemeinen verwendet, um auf Instanzen von skalaren Datentypen zu verweisen, wohingegen Instanzen anderer Typen normalerweise "Objekte" genannt werden.  
  
 **Objekt**: Der Einfachheit halber und zur Wahrung der Konsistenz wird der Begriff "Objekt" in diesem Artikel verwendet, um für jede Instanz einer Klasse oder Struktur zu beschreiben, und wenn dieser Begriff im allgemeinen Sinn verwendet wird, umfasst er alle Typen, sogar skalare Variablen.  
  
 **POD\-Typ** \(Plain Old Data\): Diese informelle Kategorie von Datentypen in C\+\+ bezieht sich auf skalare Typen \(siehe den Abschnitt "Grundlegende Typen"\) oder *POD\-Klassen*.  Eine POD\-Klasse verfügt über keine statischen Datenmember, die nicht auch PODs sind. Sie verfügt über keine benutzerdefinierten Konstruktoren, keine benutzerdefinierten Destruktoren oder keine benutzerdefinierten Zuweisungsoperatoren.  Darüber hinaus verfügt eine POD\-Klasse über keine virtuellen Funktionen, keine Basisklasse und keine privaten oder geschützten nicht statischen Datenmember.  POD\-Typen werden häufig für externen Datenaustausch verwendet, z. B. mit einem in der Programmiersprache C \(die nur über POD\-Typen verfügt\) geschriebenen Modul.  
  
## Angeben von Variablen und Funktionstypen  
 C\+\+ ist eine *stark typisierte* Sprache. Es ist auch eine *statisch typisierte* Sprache, bei der jedes Objekt über ein Typ verfügt, und dieser Typ ändert sich nie \(nicht mit Objekten der statischen Daten zu verwechseln\).            
 **Wenn Sie eine Variable deklarieren** im Code, müssen Sie entweder den Typ explizit angeben, oder Sie verwenden das `auto`\-Schlüsselwort, um den Compiler anzuweisen, den Typ aus dem Initialisierer abzuleiten.            
 **Bei Deklaration einer Funktion** im Code, müssen Sie den Typ jedes Arguments und ihres Rückgabewerts angeben, bzw. `void`, wenn kein Wert von der Funktion zurückgegeben wird.  Die Verwendung von Funktionsvorlagen, die Argumente beliebiger Typen ermöglichen stellen eine Ausnahme dar.  
  
 Nachdem Sie eine Variable deklariert haben, können Sie den Typ zu einem späteren Zeitpunkt nicht ändern.  Sie können allerdings den Wert der Variablen oder den Rückgabewert einer Funktion in eine andere Variable eines anderen Typs kopieren.  Solche Vorgänge sind unter der Bezeichnung *Typkonvertierungen* bekannt. Diese sind manchmal erforderlich aber stellen auch mögliche Quellen von Datenverlust oder Unrichtigkeit dar.  
  
 Wenn Sie eine Variable des POD\-Typs deklarieren, empfehlen wir dringend, sie zu initialisieren, ihr also einen Anfangswert zu geben.  Wenn Sie eine Variable initialisieren, verfügt sie über einen "Garbage"\-Wert, der aus allen Bits dessen besteht, das sich grade zuvor an diesem Speicherort befand.  Sich an diesen Aspekt von C\+\+ zu erinnern ist, insbesondere dann wichtig, wenn Sie vorher in einer anderen Sprache geschrieben haben, bei der die Initialisierung für Sie bearbeitet wurde.  Wenn Sie eine Variable eines Typs deklarieren, der keine POD\-Klasse ist, wird die Initialisierung vom Konstruktor behandelt.  
  
 Im folgenden Beispiel werden einige einfache Variablendeklarationen dargestellt, jeweils mit einigen Beschreibungen.  In dem Beispiel wird auch die Verwendung der Typinformationen durch den Compiler dargestellt, um bestimmte nachfolgende Vorgänge in den Variablen zuzulassen oder zu verweigern.  
  
```  
  
int result = 0;              // Declare and initialize an integer.  
double coefficient = 10.8;   // Declare and initialize a floating   
                             // point value.  
auto name = "Lady G.";       // Declare a variable and let compiler   
                             // deduce the type.  
auto address;                // error. Compiler cannot deduce a type   
                             // without an intializing value.  
age = 12;                    // error. Variable declaration must  
                             // specify a type or use auto!  
result = "Kenny G.";         // error. Can’t assign text to an int.  
string result = "zero";      // error. Can’t redefine a variable with  
                             // new type.  
int maxValue;                // Not recommended! maxValue contains   
                             // garbage bits until it is initialized.  
  
```  
  
## Grundlegende \(integrierte\) Typen  
 Im Gegensatz zu einigen Sprachen gibt es bei C\+\+ keinen universellen Basistyp, von dem alle anderen Typen abgeleitet werden.  Die [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]\-Implementierung der Sprache umfasst viele *grundlegende Typen*, die auch als *integrierte Datentypen* bekannt sind.  Das schließt numerische Typen wie `int`, `double`, `long`, `bool`, sowie `char` und `wchar_t`\-Typen für ASCII\- bzw. UNICODE\-Zeichen ein.  Die meisten grundlegenden Typen \(außer `bool`, `double`, `wchar_t` und verwandten Typen\) verfügen alle über Versionen ohne Vorzeichen. Dadurch wird der Wertebereich, den die Variable speichern kann, geändert.  Z. b. kann eine `int`\-Variable, in der eine ganze 32\-Bit\-Zahl mit Vorzeichen gespeichert wird, einen Wert von – 2.147.483.648 bis 2.147.483.647 darstellen.  Eine `unsigned int`\-Variable, die ebenfalls als 32\-Bits gespeichert wird, kann einen Wert von 0 bis 4.294.967.295 speichern.  Die Gesamtzahl der möglichen Werte ist in beiden Fällen gleich, nur der Bereich ist anders.  
  
 Die grundlegenden Typen werden vom Compiler erkannt, der über interne Regeln verfügt, die bestimmen, welche Vorgänge auf den Typen ausgeführt werden können und wie sie in andere grundlegenden Typen konvertiert werden können.  Eine vollständige Liste der integrierten Datentypen und ihrer Größe und numerischen Grenzen finden Sie unter [Grundlegende Typen](../cpp/fundamental-types-cpp.md).  
  
 In der folgende Abbildung wird die relative Größe der integrierten Datentypen dargestellt:  
  
 ![Größe integrierter Typen in Byte](../cpp/media/built-intypesizes.png "Built\-inTYpeSizes")  
  
 In der folgenden Tabelle werden die am häufigsten verwendeten grundlegenden Typen aufgelistet:  
  
|Typ|Größe|Kommentar|  
|---------|-----------|---------------|  
|int|4 Bytes|Die Standardauswahl für ganzzahlige Werte.|  
|double|8 Bytes|Die Standardauswahl für Gleitkommawerte.|  
|bool|1 Byte|Stellt Werte dar, die entweder wahr oder falsch sein können.|  
|char|1 Byte|Verwenden Sie sie für ASCII\-Zeichen in Zeichenfolgen im älteren C\-Format oder in std::string Objekten, die nie in den UNICODE konvertiert werden müssen.|  
|wchar\_t|2 Bytes|Stellt "breite" Zeichenwerte dar, die in den UNICODE\-Format codiert werden \(UTF\-16 bei Windows, andere Betriebssysteme können abweichen\).  Dies ist der Zeichentyp, der in Zeichenfolgen des Typs `std::wstring` verwendet wird.|  
|unsigned char|1 Byte|C\+\+ verfügt über keine integrierten `byte`\-Typen.  Verwenden Sie "char" ohne Vorzeichen, um einen Bytewert darzustellen.|  
|unsigned int|4 Bytes|Die Standardauswahl für Bitflags.|  
|long long|8 Bytes|Stellt sehr große ganzzahlige Werte dar.|  
  
## Der void\-Typ  
 Der `void`\-Typ ist ein besonderer Typ. Sie können eine Variable des `void`\-Typs nicht deklarieren, aber Sie können eine Variable des `void *`\-Typs deklarieren \(ein Zeiger auf `void`\). Das ist manchmal bei der Belegung von unformatiertem \(nicht typisiertem\) Arbeitsspeicher erforderlich.  Allerdings sind Zeiger auf `void` nicht typsicher, und im Allgemeinen wird von ihrer Verwendung in modernem C\+\+ abgesehen.  In der Funktionsdeklaration bedeutet ein `void`\- Rückgabewert, dass die Funktion keinen Wert zurückgibt. Das ist eine generelle und zulässige Verwendung von `void`.  Während in der Programmiersprache C Funktionen erforderlich waren, die keine Parameter `void` in der Parameterliste zu deklarieren haben, z. B. `fou(void)`, wird davon in modernem C\+\+ abgesehen und sollte `fou()` deklariert werden.  Weitere Informationen finden Sie unter [Typumwandlungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md).  
  
## const\-Typqualifizierer  
 Alle integrierten oder benutzerdefinierten Typen werden vom const\-Schlüsselwort qualifiziert.  Darüber hinaus werden Memberfunktionen möglicherweise von `const`\- qualifiziert und sogar von `const`\- überladen.  Der Wert eines `const`\-Typs kann nach der Initialisierung nicht geändert werden.  
  
```  
  
const double PI = 3.1415;  
PI = .75 //Error. Cannot modify const variable.  
  
```  
  
 Der `const`\-Qualifizierer wird in der Deklaration zahlreicher Funktion und Variablen verwendet und "const\-Richtigkeit" ist ein wichtiges Konzept in C\+\+. Im Wesentlichen bedeutet das die Verwendung von `const` zum Sicherzustellen, dass Werte zur Kompilierungszeit nicht versehentlich geändert werden.  Weitere Informationen finden Sie unter [const](../cpp/const-cpp.md).  
  
 Ein `const`\-Typ sich von seiner nicht const\-Version unterscheidet, z. B. unterscheidet sich der `const int`\-Typ vom `int`\-Typ.  Sie können den C\+\+\-Operator `const_cast` in den seltenen Situationen verwenden, in denen Sie die *const\-ness* einer Variable entfernen müssen.  Weitere Informationen finden Sie unter [Typumwandlungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md).  
  
## String\-Typen  
 Genau genommen verfügt die Programmiersprache C\+\+ über keinen integrierten "Zeichenfolge"\-Typ. `char` und einzelne `wchar_t` speichern einzelne Zeichen. Sie müssen zur Annäherung an eine Zeichenfolge ein Array dieser Typen deklarieren und dem Arrayelement nach dem letzten gültigen Zeichen einen endgültigen NULL\-Wert \(z. B. ASCII `‘\0’`\) hinzufügen \(auch als "eine Zeichenfolge im C\-Stil" bekannt\).  Für Zeichenfolgen im C\-Stil ist das Schreiben von viel mehr Code oder die Verwendung externer Hilfsprogrammbibliotheken für Zeichenfolgefunktionen erforderlich.  Aber in modernem C\+\+ werden die standardmäßige `std::string`\-Bibliothekstypen \(für `char`\-Zeichenfolgen mit 8\-Bit\) bzw. `std::wstring` \(für `wchar_t`\-Zeichenfolgen mit 16\-Bit \) genutzt.  Diese STL\-Container können als systemeigene Zeichenfolgentypen betrachtet werden, da sie Teil der Standardbibliotheken sind, die in jeder kompatiblen C\+\+\-Buildumgebung enthalten sind.  Verwenden Sie einfach die `#include <string>`\-Direktive, um diese Typen im Programm bereitzustellen. \(Wenn Sie MFC oder ATL verwenden, ist auch die CString\-Klasse verfügbar, aber Sie ist nicht Bestandteil des C\+\+\-Standards.\) Von der Verwendung von auf NULL endenden Zeichenarrays \(die bereits erwähnten Zeichenfolgen im C\-Stil\) wird im modernen C\+\+ Abstand genommen.  
  
## Benutzerdefinierte Typen  
 Wenn Sie `class`, `struct`, `union` oder `enum` definieren, wird das Konstrukt im restlichen Code wie ein grundlegender Typ verwendet.  Es verfügt über eine bekannte Größe im Arbeitsspeicher und bestimmte Regeln zur Verwendung gelten zur Kompilierzeitüberprüfung und zur Laufzeit für die Lebensdauer des Programms.  Die wichtigsten Unterschiede zwischen den grundlegenden integrierten Typen und den benutzerdefinierten Typen sind wie folgt:  
  
-   Der Compiler verfügt über kein integriertes Wissen zu einem benutzerdefinierten Typ.  Er "erfährt" vom Typ, wenn die Definition während des Kompilierungsprozesses das erste Mal auftritt.  
  
-   Sie geben an, welche Vorgänge auf dem Typ ausgeführt werden können und wie er in andere Typen konvertiert werden kann, indem Sie \(durch Überladen\) die entsprechenden Operatoren entweder als Klassenmember oder als Funktionen definieren.  Weitere Informationen finden Sie unter [Überladen \(C\+\+\)](../misc/overloading-cpp.md).  
  
-   Sie müssen nicht statisch typisiert werden \(die Regel, das sich ein Objekttyp nie ändert trifft zu\).  Durch die Mechanismen *Vererbung* und *Polymorphie* kann eine Variable, die als benutzerdefinierter Typ einer Klasse deklariert wird \(als Objektinstanz einer Klasse bezeichnet\) zur Laufzeit möglicherweise über einen anderen Typ verfügen als zur Kompilierungszeit.  Weitere Informationen finden Sie unter [Vererbung](../cpp/inheritance-cpp.md).  
  
## Zeigertypen  
 Zurückgehend zur frühesten Versionen der Programmiersprache C, können Sie in C\+\+ weiterhin eine Variable eines Zeigertyps deklarieren, indem Sie den speziellen Deklarator `*` \(Sternchen\) verwenden.  Ein Zeigertyp speichert die Adresse des Speicherorts im Arbeitsspeicher, in dem der tatsächliche Datenwert gespeichert wird.  In modernem C\+\+ werden diese als *unformatierte Zeiger* bezeichnet und im Code durch besondere Operatoren `*` \(Sternchen\) oder `->` \(Bindestrich mit Größer\-als\-Zeichen\) zugegriffen.  Dies wird *Dereferenzieren* genannt und welche der beiden Formen Sie verwenden, ist hängt davon ab, ob Sie einen Zeiger auf einen Skalarwert oder einen Zeiger auf einen Member in einem Objekt dereferenzieren.  Das Arbeiten mit Zeigertypen ist seit Langem einer der schwierigsten und verwirrendsten Aspekte bei der Programmentwicklung mit C\- und C\+\+.  In diesem Abschnitt werden einige Fakten und Vorgehensweisen beschrieben, die bei der Verwendung unformatierter Zeiger helfen sollen, wenn Sie das möchten. Aber im modernen C\+\+ ist es überhaupt nicht mehr erforderlich \(oder empfohlen\), unformatierte Zeiger für Objektbesitz zu verwenden, da der [intelligenter Zeiger](../cpp/smart-pointers-modern-cpp.md) entwickelt wurde \(mehr dazu am Ende dieses Abschnitts\).  Es ist dennoch hilfreich und sicher, unformatierte Zeiger für das Beobachten von Objekten zu verwenden. Wenn Sie sie aber für Objektbesitz verwenden müssen, sollten Sie dies mit Vorsicht tun und sich genau überlegen, wie die Objekte in deren Besitz erstellt und zerstört werden.  
  
 Als Erstes sollten Sie wissen, dass bei der Deklaration einer unformatierter Zeigervariable nur Speicher zugeordnet wird, der zum Speichern der Adresse des Speicherorts belegt wird, auf den der Zeiger verweist, wenn er dereferenziert wird.  Die Speicherbelegung für den Datenwert selbst \(auch *Sicherungsspeicher* genannt\) wurde noch nicht zugeordnet.  Das heißt, indem Sie eine unformatierte Zeigervariable deklarieren, erstellen Sie eine Speicheradressenvariable, keine tatsächliche Datenvariable.  Das Dereferenzieren einer Zeigervariable vor der Sicherstellung, dass sie eine gültige Adresse auf einen Sicherungsspeicher enthält, verursacht nicht definiertes Verhalten \(normalerweise ein schwerwiegender Fehler\) im Programm.  Im folgenden Beispiel wird die Verwendung dieses Fehlertyps veranschaulicht.  
  
```  
  
int* pNumber;       // Declare a pointer-to-int variable.  
*pNumber = 10;      // error. Although this may compile, it is  
                    // a serious error. We are dereferencing an  
                    // uninitialized pointer variable with no  
                    // allocated memory to point to.  
  
```  
  
 Das Beispiel dereferenziert einen Zeigertyp, ohne dass Arbeitsspeicher zum Speichern der tatsächlichen Ganzzahldaten belegt ist oder dass ein gültiger Speicherort zu zugewiesen wurde.  Der folgende Code korrigiert diese Fehler:  
  
```  
  
    int number = 10;          // Declare and initialize a local integer  
                              // variable for data backing store.  
    int* pNumber = &number;   // Declare and initialize a local integer  
                              // pointer variable to a valid memory  
                              // address to that backing store.  
...  
    *pNumber = 41;            // Dereference and store a new value in   
                              // the memory pointed to by  
                              // pNumber, the integer variable called  
                              // “number”. Note “number” was changed, not  
                              // “pNumber”.  
  
```  
  
 Im korrigierten Codebeispiel wird lokaler Stapelarbeitsspeicher zum Erstellen von Sicherungsspeicher, auf den `pNumber` verweist, verwendet.  Wir verwenden der Einfachheit halber einen grundlegenden Typ.  In der Praxis handelt es sich beim Sicherungsspeicher für Zeiger am häufigsten um benutzerdefinierte Typen, die in einem Bereich des Arbeitsspeichers aufgerufen werden, der *Heap* \(oder "freier Speicher "\) genannt wird, die dynamisch zugeordnet werden, indem ein `new`\-Schlüsselwortausdruck verwendet wird \(bei der alten Programmierung im C\-Stil wurde die ältere C\-Laufzeitbibliotheksfunktion `malloc()` verwendet\).  Sobald diese "Variablen" zugeordnet wurden, werden Sie normalerweise, als "Objekt" bezeichnet, insbesondere wenn sie auf einer Klassendefinition basieren.  Arbeitsspeicher, der mit `new` belegt wird, muss mithilfe einer entsprechenden `delete`\-Anweisung \(oder bei Verwendung der `malloc()`\-Funktion für die Zuordnung, mit der C\-Laufzeitfunktion `free()`\) gelöscht werden.  
  
 Das Löschen eines dynamisch zugeordneten Objekts wird jedoch schnell vergessen, besonders bei komplexem Code, der einen als *Speicherverlust* bezeichneten Ressourcenfehler verursacht.  Aus diesem Grund wird vor der Verwendung unformatierter Zeigern in modernem C\+\+ abgesehen.  Es ist fast immer besser, einen unformatierten Zeiger in einen [intelligenten Zeiger](../cpp/smart-pointers-modern-cpp.md) einzuschließen, der den Arbeitsspeicher automatisch freigibt, sobald sein Destruktor aufgerufen wird \(wenn der Code den Bereich für den intelligenten Zeiger verlässt\). Mit der Verwendung von intelligenten Zeigern vermeiden Sie praktisch eine ganze Fehlerklasse in Ihren C\+\+\-Programmen.  Im folgenden Beispiel wird angenommen, dass `MyClass` ein benutzerdefinierter Typ ist, der eine öffentliche Methode `DoSomeWork();` umfasst.  
  
```  
  
void someFunction() {  
    unique_ptr<MyClass> pMc(new MyClass);  
    pMc->DoSomeWork();  
}  
  // No memory leak. Out-of-scope automatically calls the destructor  
  // for the unique_ptr, freeing the resource.  
  
```  
  
 Weitere Informationen zu intelligenten Zeigern finden Sie unter [Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md).  
  
 Weitere Informationen über Zeigerkonvertierungen finden Sie unter [Typumwandlungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md).  
  
 Weitere Informationen über Zeiger im Allgemeinen finden Sie unter [Zeiger](../cpp/pointers-cpp.md).  
  
## Windows\-Datentypen  
 In der klassischen Win32\-Programmierung für C und C\+\+ verwenden die meisten Funktionen Windows\-spezifische Typdefinitionen und \#define\-Makros \(die in `windef.h` definiert sind\), um die Typen von Parametern und Rückgabewerten anzugeben.  Diese "Windows\-Datentypen" sind meistens nur die speziellen Namen \(Alias\) für integrierte C\/C\+\+\-Datentypen.  Eine vollständige Liste dieser Typdefinitionen und Präprozessordefinitionen finden Sie unter [Windows Data Types](assetId:///4553cafc-450e-4493-a4d4-cb6e2f274d46).  Einige dieser Typdefinitionen, wie HRESULT und LCID, sind nützlich und beschreibend.  Andere, wie INT, haben keine besondere Bedeutung und sind nur Alias für grundlegende C\+\+\-Typen.  Weitere Windows\-Datentypen haben Namen, die seit den Tagen der C\-Programmierung und der 16\-Bit\-Prozessoren beibehalten werden. Sie haben keinen Zweck oder keine Bedeutung mehr bei moderner Hardware oder Betriebssystemen.  Es gibt auch speziellen Datentypen, die der Windows Runtime\-Bibliothek zugeordnet sind Sie werden als [Windows Runtime base data types](assetId:///b5735851-ec07-48c1-92b4-ca9f768096f6) aufgeführt.  Für modernes C\+\+ gilt die allgemeine Richtlinie, die grundlegenden C\+\+\-Typen vorzuziehen, es sei denn, mit dem Windows\-Typ wird zusätzliche Bedeutung über die Interpretationsweise des Werts kommuniziert.  
  
## Weitere Informationen  
 Weitere Informationen zum Typsystem von C\+\+ finden Sie in den folgenden Themen.  
  
|||  
|-|-|  
|[Werttypen](../cpp/value-types-modern-cpp.md)|Beschreibt *Werttypen* und die Probleme, die bei ihrer Verwendung auftreten können.|  
|[Typumwandlungen und Typsicherheit](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Beschreibt allgemeine Typkonvertierungsprobleme und zeigt, wie sie vermieden werden.|  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)