---
title: "#import-Direktive (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "#import"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import-Direktive"
  - "TLH-Dateien"
  - "COM, Typbibliotheks-Headerdatei"
  - "Import-Direktive (#import)"
  - "Präprozessor, Direktiven"
  - "tlbid-Switch"
  - "tlh-Dateien"
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# #import-Direktive (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Wird verwendet, um Informationen aus einer Typbibliothek zu integrieren.  Der Inhalt der Typbibliothek wird in C\+\+\-Klassen konvertiert, die größtenteils die COM\-Schnittstellen beschreiben.  
  
## Syntax  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
#### Parameter  
 *filename*  
 Gibt die zu importierende Typbibliothek an.  `filename` kann eines der folgenden Elemente sein:  
  
-   Der Name einer Datei, die eine Typbibliothek enthält, z. B. eine OLB\-, TLB\- oder DLL\-Datei.  Das Schlüsselwort **file:** kann jedem Dateinamen vorangestellt sein.  
  
-   Die ProgID eines Steuerelements in der Typbibliothek.  Das Schlüsselwort **progid:** kann jeder ProgID vorangestellt sein.  Beispiel:  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     Weitere Informationen zu ProgIDs finden Sie unter [Angeben der Lokalisierungs\-ID und der Versionsnummer](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).  
  
     Beachten Sie, dass beim Kompilieren mit einem Cross\-Compiler auf einem 64\-Bit\-Betriebssystem der Compiler nur die 32\-Bit\-Registrierungsstruktur lesen kann.  Sie sollten den systemeigenen 64\-Bit\-Compiler verwenden, um eine 64\-Bit\-Typbibliothek zu erstellen und zu registrieren.  
  
-   Die Bibliotheks\-ID der Typbibliothek.  Das Schlüsselwort **libid:** kann jeder Bibliotheks\-ID vorangestellt sein.  Beispiel:  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     Wenn Sie keine Version oder LCID angeben, werden [Regeln](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber), die auf **progid:** angewendet werden, auch auf **libid:** angewendet.  
  
-   Ein ausführbare Datei \(EXE\-Datei\).  
  
-   Eine Bibliotheksdatei \(DLL\-Datei\), die eine Typbibliotheksressource enthält \(z. B. OCX\-Datei\).  
  
-   Ein Verbunddokument, das eine Typbibliothek enthält.  
  
-   Jedes andere Dateiformat, das von der **LoadTypeLib**\-API interpretiert werden kann.  
  
 `attributes`  
 Mindestens ein [\#import\-Attribut](#_predir_the_23import_directive_import_attributes).  Trennen Sie Attribute entweder mit einem Komma oder einem Leerzeichen.  Beispiel:  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
 \-oder\-  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## Hinweise  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a> Suchreihenfolge für Dateinamen  
 *filename* ist optional eine Verzeichnisangabe vorangestellt.  Der Dateiname muss eine vorhandene Datei benennen.  Der Unterschied zwischen den beiden Syntaxformen liegt in der Reihenfolge, in der der Präprozessor nach den Typbibliotheksdateien sucht, wenn der Pfad unvollständig angegeben wird.  
  
|Syntaxformat|Aktion|  
|------------------|------------|  
|Format mit Anführungszeichen|Weist den Präprozessor an, nach Typbibliotheksdateien zuerst im Verzeichnis der Datei, die die `#import`\-Anweisung enthält, und dann in den Verzeichnissen beliebiger Dateien, die diese Datei enthalten \(`#include`\), zu suchen.  Der Präprozessor sucht dann in den unten aufgeführten Verzeichnissen.|  
|Format mit spitzer Klammer|Weist den Präprozessor an, nach Typbibliotheksdateien in den folgenden Verzeichnissen zu suchen:<br /><br /> 1.  Die **PATH**\-Umgebungsvariablen\-Pfadliste<br />2.  Die **LIB**\-Umgebungsvariablen\-Pfadliste<br />3.  Der Pfad, der von der \/I\-Compileroption \(zusätzliche Includeverzeichnisse\) angegeben wird \(es sei denn, der Compiler sucht nach einer Typbibliothek, auf die von einer anderen Typbibliothek mit dem [no\_registry](../preprocessor/no-registry.md)\-Attribut verwiesen wurde.\)|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> Angeben der Lokalisierungs\-ID und der Versionsnummer  
 Wenn Sie eine ProgID angeben, können Sie auch die Lokalisierungs\-ID und die Versionsnummer der ProgID angeben.  Beispiel:  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
 Wenn Sie keine Lokalisierungs\-ID angeben, wird eine ProgID gemäß den folgenden Regeln ausgewählt:  
  
-   Wenn nur eine Lokalisierungs\-ID vorhanden ist, wird diese verwendet.  
  
-   Wenn mehr als eine Lokalisierungs\-ID vorhanden ist, wird die erste mit der Versionsnummer 0, 9 oder 409 verwendet.  
  
-   Wenn mehr als eine Lokalisierungs\-ID vorhanden ist und keine von ihnen 0, 9 oder 409 ist, wird die letzte verwendet.  
  
-   Wenn Sie keine Versionsnummer angeben, wird die neueste Version verwendet.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> Headerdateien, die durch Importieren erstellt wurden  
 `#import` erstellt zwei Headerdateien, die den Inhalt der Typbibliothek in C\+\+\-Quellcode wiederherstellen.  Die primäre Headerdatei entspricht der Datei, die vom MIDL\-Compiler \(Microsoft Interface Definition Language\) erstellt wird, sie verfügt jedoch über zusätzlichen vom Compiler generierten Code und Daten.  Die [primäre Headerdatei](#_predir_the_primary_type_library_header_file) hat den gleichen Basisnamen wie die Typbibliothek sowie eine TLH\-Erweiterung.  Die sekundäre Headerdatei weist den gleichen Basisnamen wie die Typbibliothek auf, mit einer TLI\-Erweiterung.  Sie enthält die Implementierungen für vom Compiler generierte Memberfunktionen und wird in die primäre Headerdatei eingefügt \(`#include`\).  
  
 Beim Importieren einer dispinterface\-Eigenschaft, die byref\-Parameter verwendet, generiert \#import keine \_\_declspec\([property](../cpp/property-cpp.md)\)\-Anweisung für die Funktion.  
  
 Beide Headerdateien werden in das Ausgabeverzeichnis eingefügt, das durch die \/Fo\-Option \(Name der Objektdatei\) festgelegt wird.  Sie werden dann vom Compiler gelesen und kompiliert, als wäre die primäre Headerdatei durch eine `#include`\-Direktive benannt.  
  
 Die folgenden Compileroptimierungen sind in der `#import`\-Direktive enthalten:  
  
-   Wenn sie erstellt wird, wird der Headerdatei der gleiche Zeitstempel gegeben wie der Typbibliothek.  
  
-   Wenn `#import` verarbeitet wird, überprüft der Compiler zuerst, ob der Header vorhanden und aktuell ist.  Wenn ja, muss er nicht neu erstellt werden.  
  
 Die `#import`\-Direktive ist auch an der minimalen Neuerstellung beteiligt und kann in eine vorkompilierte Headerdatei eingefügt werden.  Weitere Informationen finden Sie unter [Erstellen vorkompilierter Headerdateien](../build/reference/creating-precompiled-header-files.md).  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> Primäre Typbibliotheks\-Headerdatei  
 Die primäre Headerdatei der Typbibliothek umfasst sieben Abschnitte:  
  
-   Textbaustein für Überschrift: Besteht aus Kommentaren, der `#include`\-Anweisung für COMDEF.H \(das mehrere Standardmakros definiert, die im Header verwendet werden\) und weiteren verschiedenen Setupinformationen.  
  
-   Vorwärtsverweise und Typdefinitionen: Bestehen aus Strukturdeklarationen wie `struct IMyInterface` und Typdefinitionen.  
  
-   Deklarationen für intelligente Zeiger: Die `_com_ptr_t`\-Vorlagenklasse ist eine Implementierung des intelligenten Zeigers, die Schnittstellenzeiger kapselt und dafür sorgt, dass der Aufruf der Funktionen `AddRef`, **Release** und `QueryInterface` nicht erforderlich ist.  Darüber hinaus blendet es den `CoCreateInstance`\-Aufruf aus, wenn ein neues COM\-Objekt erstellt wird.  In diesem Abschnitt wird die Makroanweisung **\_COM\_SMARTPTR\_TYPEDEF** zum Festlegen von Typdefinitionen von COM\-Schnittstellen als Vorlagenspezialisierungen der [\_com\_ptr\_t](../cpp/com-ptr-t-class.md)\-Vorlagenklasse verwendet.  Zum Beispiel für die **IMyInterface**\-Schnittstelle enthält die TLH\-Datei Folgendes:  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     Dies wird vom Compiler zu Folgendem erweitert:  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     Typ `IMyInterfacePtr` kann dann anstelle des nicht formatierten Schnittstellenzeigers `IMyInterface*` verwendet werden.  Daher ist es nicht erforderlich, die verschiedenen **IUnknown**\-Memberfunktionen aufzurufen.  
  
-   Typinformationsdeklarationen: Bestehen hauptsächlich aus Klassendefinitionen und anderen Elementen, die die einzelnen typeinfo\-Elemente verfügbar machen, die von **ITypeLib:GetTypeInfo** zurückgegeben werden.  In diesem Abschnitt wird jede Typinformation aus der Typbibliothek im Header in einem Format wiedergegeben, das von den `TYPEKIND`\-Informationen abhängt.  
  
-   Definition der optionalen GUID im alten Format: Enthält Initialisierungen der benannten GUID\-Konstanten.  Dies sind Namen im Format **CLSID\_CoClass** und **IID\_Interface**, vergleichbar mit denen, die vom MIDL\-Compiler generiert werden.  
  
-   `#include`\-Anweisung für den sekundären Header der Typbibliothek.  
  
-   Textbaustein für Footer: Schließt aktuell `#pragma pack(pop)` ein.  
  
 Alle Abschnitte, außer der Abschnitte über Textbausteine für Überschrift und Footer, werden in einen Namespace mit dessen Namen eingeschlossen, der von der **library**\-Anweisung in der ursprünglichen IDL\-Datei angegeben wird.  Sie können die Namen des Typbibliotheksheaders entweder über eine explizite Qualifizierung mit dem Namespacenamen verwenden oder indem Sie die Anweisung  
  
```  
using namespace MyLib;  
```  
  
 unmittelbar nach der `#import`\-Anweisung im Quellcode einfügen.  
  
 Der Namespace kann mithilfe des [no\_namespace](#_predir_no_namespace)\-Attributs der `#import`\-Direktive unterdrückt werden.  Allerdings kann das Unterdrücken des Namespace zu Namenskonflikten führen.  Der Namespace kann mithilfe des [rename\_namespace](#_predir_rename_namespace)\-Attributs neu benannt werden.  
  
 Der Compiler stellt den vollständigen Pfad zu einer beliebigen Typbibliotheksabhängigkeit bereit, die von der Typbibliothek benötigt wird, die gerade verarbeitet wird.  Der Pfad wird in Form von Kommentaren in den Header der Typbibliothek \(.TLH\) geschrieben, den der Compiler für jede verarbeitete Typbibliothek erstellt.  
  
 Wenn eine Typbibliothek Verweise auf Typen enthält, die in anderen Typbibliotheken definiert sind, dann enthält die TLH\-Datei Kommentare folgender Art:  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
 Der tatsächliche Name der Datei im `#import`\-Kommentar ist der vollständige Pfad der übergreifenden Typbibliothek, wie er in der Registrierung gespeichert ist.  Wenn Fehler aufgrund fehlender Typdefinitionen auftreten, überprüfen Sie die Kommentare am Anfang der TLH\-Datei, um festzustellen, welche abhängigen Typbibliotheken möglicherweise zuerst importiert werden müssen.  Wahrscheinliche Fehler sind Syntaxfehler \(z. B. C2143, C2146, C2321\), C2501 \(fehlende decl\-Spezifizierer\) oder C2433 \("inline" bei Datendeklaration nicht zulässig\) beim Kompilieren der TLI\-Datei.  
  
 Sie müssen ermitteln, welche der Abhängigkeitskommentare von Systemheadern nicht anderweitig bereitgestellt werden, und dann eine `#import`\-Direktive bereitstellen, bevor die `#import`\-Direktive der abhängigen Typbibliothek die Fehler behebt.  
  
 Weitere Informationen finden Sie im Knowledge Base\-Artikel über mögliche Zugriffsverletzungen durch \#import\-Wrappermethoden \(Q242527\) oder im Artikel über Compilerfehler bei der Verwendung von \#import mit XML \(Q269194\).  Sie finden Knowledge Base\-Artikel in MSDN Library\-Medien oder unter [http:\/\/support.microsoft.com\/support\/](http://support.microsoft.com/support/).  
  
##  <a name="_predir_the_23import_directive_import_attributes"></a> \#import\-Attribute  
 `#import` kann optional ein oder mehrere Attribute einschließen.  Diese Attribute weisen den Compiler an, den Inhalt der Typbibliotheksheader zu ändern.  Ein umgekehrter Schrägstrich \(**\\**\) kann verwendet werden, um zusätzliche Zeilen in einer einzelnen `#import`\-Anweisung einzufügen.  Beispiel:  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
 Weitere Informationen finden Sie unter [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md).  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)   
 [COM\-Unterstützung des Compilers](../cpp/compiler-com-support.md)