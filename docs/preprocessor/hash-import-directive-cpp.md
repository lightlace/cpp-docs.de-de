---
title: '#Importieren der Richtlinie (C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#import'
dev_langs:
- C++
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cbf8a35022638884733f5151fffb2a3a0a2946c3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="import-directive-c"></a>#import-Anweisung (C++)
**C++-spezifisch**  
  
 Wird verwendet, um Informationen aus einer Typbibliothek zu integrieren. Der Inhalt der Typbibliothek wird in C++-Klassen konvertiert, die größtenteils die COM-Schnittstellen beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
#### <a name="parameters"></a>Parameter  
 *filename*  
 Gibt die zu importierende Typbibliothek an. `filename` kann eines der folgenden Elemente sein:  
  
-   Der Name einer Datei, die eine Typbibliothek enthält, z. B. eine OLB-, TLB- oder DLL-Datei. Das Schlüsselwort **Datei:**, kann jedem Dateinamen vorangestellt sein.  
  
-   Die ProgID eines Steuerelements in der Typbibliothek. Das Schlüsselwort **progid:**, kann jeder progid vorangestellt sein. Zum Beispiel:  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     Weitere Informationen zu Progids finden Sie unter [angeben der Lokalisierungs-ID und Versionsnummer](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).  
  
     Beachten Sie, dass beim Kompilieren mit einem Cross-Compiler auf einem 64-Bit-Betriebssystem der Compiler nur die 32-Bit-Registrierungsstruktur lesen kann. Sie sollten den systemeigenen 64-Bit-Compiler verwenden, um eine 64-Bit-Typbibliothek zu erstellen und zu registrieren.  
  
-   Die Bibliotheks-ID der Typbibliothek. Das Schlüsselwort **Libid:**, kann jede Bibliothek-ID vorangestellt Zum Beispiel:  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     Wenn Sie keine Version oder Lcid angeben der [Regeln](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) , gelten für **progid:** gelten auch für **Libid:**.  
  
-   Ein ausführbare Datei (EXE-Datei).  
  
-   Eine Bibliotheksdatei (DLL-Datei), die eine Typbibliotheksressource enthält (z. B. OCX-Datei).  
  
-   Ein Verbunddokument, das eine Typbibliothek enthält.  
  
-   Jedes andere Dateiformat, das von verarbeitet werden kann die **LoadTypeLib** API.  
  
 `attributes`  
 Eine oder mehrere [#import-Attribute](#_predir_the_23import_directive_import_attributes). Trennen Sie Attribute entweder mit einem Komma oder einem Leerzeichen. Zum Beispiel:  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
 - oder -   
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## <a name="remarks"></a>Hinweise  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a> Suchreihenfolge für Dateinamen  
 *FileName* optional eine Verzeichnisangabe vorangestellt ist. Der Dateiname muss eine vorhandene Datei benennen. Der Unterschied zwischen den beiden Syntaxformen liegt in der Reihenfolge, in der der Präprozessor nach den Typbibliotheksdateien sucht, wenn der Pfad unvollständig angegeben wird.  
  
|Syntaxformat|Aktion|  
|-----------------|------------|  
|Format mit Anführungszeichen|Weist den Präprozessor an, nach Typbibliotheksdateien zuerst im Verzeichnis der Datei, die die `#import`-Anweisung enthält, und dann in den Verzeichnissen beliebiger Dateien, die diese Datei enthalten (`#include`), zu suchen. Der Präprozessor sucht dann in den unten aufgeführten Verzeichnissen.|  
|Format mit spitzer Klammer|Weist den Präprozessor an, nach Typbibliotheksdateien in den folgenden Verzeichnissen zu suchen:<br /><br /> 1.  Die **Pfad** Umgebungsvariablen-Pfadliste<br />2.  Die **LIB** Umgebungsvariablen-Pfadliste<br />3.  Der Pfad angegeben, durch die/i (Zusätzliche Includeverzeichnisse) (Compileroption), außer es sucht der Compiler eine Typbibliothek, die aus einer anderen Typbibliothek mit verwiesen wurde die [No_registry](../preprocessor/no-registry.md) Attribut.|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> Angeben der Lokalisierungs-ID und Versionsnummer  
 Wenn Sie eine ProgID angeben, können Sie auch die Lokalisierungs-ID und die Versionsnummer der ProgID angeben. Zum Beispiel:  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
 Wenn Sie keine Lokalisierungs-ID angeben, wird eine ProgID gemäß den folgenden Regeln ausgewählt:  
  
-   Wenn nur eine Lokalisierungs-ID vorhanden ist, wird diese verwendet.  
  
-   Wenn mehr als eine Lokalisierungs-ID vorhanden ist, wird die erste mit der Versionsnummer 0, 9 oder 409 verwendet.  
  
-   Wenn mehr als eine Lokalisierungs-ID vorhanden ist und keine von ihnen 0, 9 oder 409 ist, wird die letzte verwendet.  
  
-   Wenn Sie keine Versionsnummer angeben, wird die neueste Version verwendet.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> Header-Dateien, die durch Importvorgang erstellt werden  
 `#import` erstellt zwei Headerdateien, die den Inhalt der Typbibliothek in C++-Quellcode wiederherstellen. Die primäre Headerdatei entspricht der Datei, die vom MIDL-Compiler (Microsoft Interface Definition Language) erstellt wird, sie verfügt jedoch über zusätzlichen vom Compiler generierten Code und Daten. Die [primäre Headerdatei](#_predir_the_primary_type_library_header_file) hat den gleichen Basisnamen wie die Typbibliothek sowie eine. TLH-Erweiterung. Die sekundäre Headerdatei weist den gleichen Basisnamen wie die Typbibliothek auf, mit einer TLI-Erweiterung. Sie enthält die Implementierungen für vom Compiler generierte Memberfunktionen und wird in die primäre Headerdatei eingefügt (`#include`).  
  
 Beim Importieren eine Dispinterface-Eigenschaft, die Byref-Parametern verwendet, generiert #import keine __declspec ([Eigenschaft](../cpp/property-cpp.md))-Anweisung für die Funktion.  
  
 Beide Headerdateien werden in das Ausgabeverzeichnis eingefügt, das durch die /Fo-Option (Name der Objektdatei) festgelegt wird. Sie werden dann vom Compiler gelesen und kompiliert, als wäre die primäre Headerdatei durch eine `#include`-Direktive benannt.  
  
 Die folgenden Compileroptimierungen sind in der `#import`-Direktive enthalten:  
  
-   Wenn sie erstellt wird, wird der Headerdatei der gleiche Zeitstempel gegeben wie der Typbibliothek.  
  
-   Wenn `#import` verarbeitet wird, überprüft der Compiler zuerst, ob der Header vorhanden und aktuell ist. Wenn ja, muss er nicht neu erstellt werden.  
  
 Die `#import`-Direktive ist auch an der minimalen Neuerstellung beteiligt und kann in eine vorkompilierte Headerdatei eingefügt werden. Finden Sie unter [Erstellen vorkompilierter Headerdateien](../build/reference/creating-precompiled-header-files.md) für Weitere Informationen.  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> Primäre Typbibliotheks-Headerdatei  
 Die primäre Headerdatei der Typbibliothek umfasst sieben Abschnitte:  
  
-   Textbaustein für Überschrift: Besteht aus Kommentaren, der `#include`-Anweisung für COMDEF.H (das mehrere Standardmakros definiert, die im Header verwendet werden) und weiteren verschiedenen Setupinformationen.  
  
-   Vorwärtsverweise und Typdefinitionen: Bestehen aus Strukturdeklarationen wie `struct IMyInterface` und Typdefinitionen.  
  
-   Deklarationen für intelligente Zeiger: die Vorlagenklasse `_com_ptr_t` ist eine Implementierung des intelligenten Zeigers, die Schnittstellenzeiger kapselt und entfällt die Notwendigkeit, rufen Sie `AddRef`, **Release**, `QueryInterface` Funktionen. Darüber hinaus blendet es den `CoCreateInstance`-Aufruf aus, wenn ein neues COM-Objekt erstellt wird. Dieser Abschnitt verwendet die makroanweisung **_COM_SMARTPTR_TYPEDEF** Typdefinitionen von COM-Schnittstellen als vorlagenspezialisierungen der herstellen die [_com_ptr_t](../cpp/com-ptr-t-class.md) Vorlagenklasse. Z. B. für Schnittstelle **IMyInterface**die. TLH-Datei enthält:  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     Dies wird vom Compiler zu Folgendem erweitert:  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     Typ `IMyInterfacePtr` kann dann anstelle des nicht formatierten Schnittstellenzeigers `IMyInterface*` verwendet werden. Folglich besteht keine Notwendigkeit, rufen Sie die verschiedenen **IUnknown** Memberfunktionen  
  
-   Typinformationsdeklarationen: bestehen hauptsächlich aus Klassendefinitionen und anderen Elementen, die die einzelnen Typeinfo-Elemente zurückgegebenes verfügbar machen, **ITypeLib: GetTypeInfo**. In diesem Abschnitt wird jede Typinformation aus der Typbibliothek im Header in einem Format wiedergegeben, das von den `TYPEKIND`-Informationen abhängt.  
  
-   Definition der optionalen GUID im alten Format: Enthält Initialisierungen der benannten GUID-Konstanten. Dies sind die Namen der Form **CLSID_CoClass** und **IID_Interface**, vergleichbar mit denen vom MIDL-Compiler generiert.  
  
-   `#include`-Anweisung für den sekundären Header der Typbibliothek.  
  
-   Textbaustein für Footer: Schließt aktuell `#pragma pack(pop)` ein.  
  
 Alle Abschnitte, außer den Spaltenüberschrift Textbausteine und eine Fußzeile Textbaustein, in einem Namespace eingeschlossen sind, mit dem Namen gemäß der **Bibliothek** Anweisung in der ursprünglichen IDL-Datei. Sie können die Namen des Typbibliotheksheaders entweder über eine explizite Qualifizierung mit dem Namespacenamen verwenden oder indem Sie die Anweisung  
  
```  
using namespace MyLib;  
```  
  
 unmittelbar nach der `#import`-Anweisung im Quellcode einfügen.  
  
 Der Namespace kann unterdrückt werden, mithilfe der [No_namespace](#_predir_no_namespace) Attribut von der `#import` Richtlinie. Allerdings kann das Unterdrücken des Namespace zu Namenskonflikten führen. Der Namespace kann auch umbenannt werden, indem die [Rename_namespace](#_predir_rename_namespace) Attribut.  
  
 Der Compiler stellt den vollständigen Pfad zu einer beliebigen Typbibliotheksabhängigkeit bereit, die von der Typbibliothek benötigt wird, die gerade verarbeitet wird. Der Pfad wird in Form von Kommentaren in den Header der Typbibliothek (.TLH) geschrieben, den der Compiler für jede verarbeitete Typbibliothek erstellt.  
  
 Wenn eine Typbibliothek Verweise auf Typen enthält, die in anderen Typbibliotheken definiert sind, dann enthält die TLH-Datei Kommentare folgender Art:  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
 Der tatsächliche Name der Datei im `#import`-Kommentar ist der vollständige Pfad der übergreifenden Typbibliothek, wie er in der Registrierung gespeichert ist. Wenn Fehler aufgrund fehlender Typdefinitionen auftreten, überprüfen Sie die Kommentare am Anfang der TLH-Datei, um festzustellen, welche abhängigen Typbibliotheken möglicherweise zuerst importiert werden müssen. Wahrscheinliche Fehler sind Syntaxfehler (z. B. C2143, C2146, C2321), C2501 (fehlende decl-Spezifizierer) oder C2433 ("inline" bei Datendeklaration nicht zulässig) beim Kompilieren der TLI-Datei.  
  
 Sie müssen ermitteln, welche der Abhängigkeitskommentare von Systemheadern nicht anderweitig bereitgestellt werden, und dann eine `#import`-Direktive bereitstellen, bevor die `#import`-Direktive der abhängigen Typbibliothek die Fehler behebt.  
  
 Weitere Informationen finden Sie im Knowledge Base-Artikel über mögliche Zugriffsverletzungen durch #import-Wrappermethoden (Q242527) oder im Artikel über Compilerfehler bei der Verwendung von #import mit XML (Q269194). Sie finden Knowledge Base-Artikeln auf der MSDN Library-Medien oder unter [Microsoft-Support](https://support.microsoft.com/).  
  
##  <a name="_predir_the_23import_directive_import_attributes"></a> #import-Attribute  
 `#import` kann optional ein oder mehrere Attribute einschließen. Diese Attribute weisen den Compiler an, den Inhalt der Typbibliotheksheader zu ändern. Ein umgekehrter Schrägstrich (**\\**) Symbol kann verwendet werden, um zusätzliche Zeilen in einer einzelnen einschließen `#import` Anweisung. Zum Beispiel:  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
 Weitere Informationen finden Sie unter [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md).  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)   
 [COM-Unterstützung des Compilers](../cpp/compiler-com-support.md)
