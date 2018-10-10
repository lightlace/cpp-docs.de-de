---
title: '#Import-Anweisung (C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60397fea85e3fd121469ae4568dac18fa6b9ddb1
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890321"
---
# <a name="import-directive-c"></a>#import-Anweisung (C++)
**C++-spezifisch**  
  
Wird verwendet, um Informationen aus einer Typbibliothek zu integrieren. Der Inhalt der Typbibliothek wird in C++-Klassen konvertiert, die größtenteils die COM-Schnittstellen beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
### <a name="parameters"></a>Parameter  
*filename*  
Gibt die zu importierende Typbibliothek an. *FileName* kann einen der folgenden sein:  
  
- Der Name einer Datei, die eine Typbibliothek enthält, z. B. eine OLB-, TLB- oder DLL-Datei. Das Schlüsselwort **Datei:**, kann die jedem Dateinamen vorangestellt sein.  
  
- Die ProgID eines Steuerelements in der Typbibliothek. Das Schlüsselwort **progid:**, kann jeder progid vorangestellt sein. Zum Beispiel:  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     Weitere Informationen zu Progids finden Sie unter [angeben der Lokalisierungs-ID und Versionsnummer](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).  
  
     Beachten Sie, dass beim Kompilieren mit einem Cross-Compiler auf einem 64-Bit-Betriebssystem der Compiler nur die 32-Bit-Registrierungsstruktur lesen kann. Sie sollten den systemeigenen 64-Bit-Compiler verwenden, um eine 64-Bit-Typbibliothek zu erstellen und zu registrieren.  
  
- Die Bibliotheks-ID der Typbibliothek. Das Schlüsselwort **Libid:**, können jede Bibliothek-ID voranstellen Zum Beispiel:  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     Wenn Sie keine Version oder Lcid angeben der [Regeln](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) , gelten für **progid:** gelten auch für **Libid:**.  
  
- Ein ausführbare Datei (EXE-Datei).  
  
- Eine Bibliotheksdatei (DLL-Datei), die eine Typbibliotheksressource enthält (z. B. OCX-Datei).  
  
- Ein Verbunddokument, das eine Typbibliothek enthält.  
  
- Jedes andere Dateiformat, das von erkannt werden kann die **LoadTypeLib** API.  
  
*Attribute*  
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
|Format mit Anführungszeichen|Weist den Präprozessor an, nach Typbibliotheksdateien zuerst im Verzeichnis der Datei gesucht werden soll, enthält die **#import** -Anweisung, und klicken Sie dann in den Verzeichnissen beliebiger Dateien, die enthalten (`#include`) die Datei. Der Präprozessor sucht dann in den unten aufgeführten Verzeichnissen.|  
|Format mit spitzer Klammer|Weist den Präprozessor an, nach Typbibliotheksdateien in den folgenden Verzeichnissen zu suchen:<br /><br /> 1.  Die `PATH` Umgebungsvariablen-Pfadliste<br />2.  Die `LIB` Umgebungsvariablen-Pfadliste<br />3.  Durch die/i angegebenen Pfad (Zusätzliche Includeverzeichnisse)-Compileroption verwenden, es sei denn, es der Compiler sucht nach einer Typbibliothek, die von einer anderen Typbibliothek mit verwiesen wurde die [No_registry](../preprocessor/no-registry.md) Attribut.|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> Angeben der Lokalisierungs-ID und Versionsnummer  

Wenn Sie eine ProgID angeben, können Sie auch die Lokalisierungs-ID und die Versionsnummer der ProgID angeben. Zum Beispiel:  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
Wenn Sie keine Lokalisierungs-ID angeben, wird eine ProgID gemäß den folgenden Regeln ausgewählt:  
  
- Wenn nur eine Lokalisierungs-ID vorhanden ist, wird diese verwendet.  
  
- Wenn mehr als eine Lokalisierungs-ID vorhanden ist, wird die erste mit der Versionsnummer 0, 9 oder 409 verwendet.  
  
- Wenn mehr als eine Lokalisierungs-ID vorhanden ist und keine von ihnen 0, 9 oder 409 ist, wird die letzte verwendet.  
  
- Wenn Sie keine Versionsnummer angeben, wird die neueste Version verwendet.  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> Header-Dateien, die durch Importvorgang erstellt werden  

**#import** erstellt zwei Headerdateien, die die den Inhalt der Typbibliothek in C++-Quellcode zu rekonstruieren. Die primäre Headerdatei entspricht der Datei, die vom MIDL-Compiler (Microsoft Interface Definition Language) erstellt wird, sie verfügt jedoch über zusätzlichen vom Compiler generierten Code und Daten. Die [primäre Headerdatei](#_predir_the_primary_type_library_header_file) hat den gleichen Basisnamen wie die Typbibliothek, gefolgt von einem. TLH-Erweiterung. Die sekundäre Headerdatei weist den gleichen Basisnamen wie die Typbibliothek auf, mit einer TLI-Erweiterung. Sie enthält die Implementierungen für vom Compiler generierte Memberfunktionen und wird in die primäre Headerdatei eingefügt (`#include`).  
  
Beim Importieren einer Dispinterface-Eigenschaft, die Byref-Parameter wird verwendet, generiert #import keine __declspec ([Eigenschaft](../cpp/property-cpp.md))-Anweisung für die Funktion.  
  
Beide Headerdateien werden in das Ausgabeverzeichnis eingefügt, das durch die /Fo-Option (Name der Objektdatei) festgelegt wird. Sie werden dann vom Compiler gelesen und kompiliert, als wäre die primäre Headerdatei durch eine `#include`-Anweisung benannt.  
  
Die folgenden compileroptimierungen sind in der **#import** Richtlinie:  
  
- Wenn sie erstellt wird, wird der Headerdatei der gleiche Zeitstempel gegeben wie der Typbibliothek.  
  
- Wenn **#import** wird verarbeitet, der Compiler überprüft zuerst, ob der Header vorhanden ist und auf dem neuesten Stand ist. Wenn ja, muss er nicht neu erstellt werden.  
  
Die **#import** Richtlinie auch minimalen Neuerstellung beteiligt und in eine vorkompilierte Headerdatei eingefügt werden können. Finden Sie unter [Erstellen vorkompilierter Headerdateien](../build/reference/creating-precompiled-header-files.md) für Weitere Informationen.  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> Primäre Typbibliotheks-Headerdatei  
Die primäre Headerdatei der Typbibliothek umfasst sieben Abschnitte:  
  
- Textbaustein für Überschrift: Besteht aus Kommentaren, der `#include`-Anweisung für COMDEF.H (das mehrere Standardmakros definiert, die im Header verwendet werden) und weiteren verschiedenen Setupinformationen.  
  
- Vorwärtsverweise und Typdefinitionen: Bestehen aus Strukturdeklarationen wie `struct IMyInterface` und Typdefinitionen.  
  
- Deklarationen für intelligente Zeiger: die Vorlagenklasse `_com_ptr_t` ist eine Implementierung des intelligenten Zeigers, die Schnittstellenzeiger kapselt und entfällt die Notwendigkeit, rufen Sie `AddRef`, `Release`, `QueryInterface` Funktionen. Darüber hinaus blendet es den `CoCreateInstance`-Aufruf aus, wenn ein neues COM-Objekt erstellt wird. In diesem Abschnitt wird die makroanweisung `_COM_SMARTPTR_TYPEDEF` herstellen Typdefinitionen von COM-Schnittstellen für die vorlagenspezialisierungen der werden die [_com_ptr_t](../cpp/com-ptr-t-class.md) Vorlagenklasse. Z. B. für Schnittstelle `IMyInterface`,. TLH-Datei enthält Folgendes:  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     Dies wird vom Compiler zu Folgendem erweitert:  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     Typ `IMyInterfacePtr` kann dann anstelle des nicht formatierten Schnittstellenzeigers `IMyInterface*` verwendet werden. Daher besteht keine Notwendigkeit zum Aufrufen der verschiedenen `IUnknown` Memberfunktionen  
  
- Typinformationsdeklarationen: bestehen hauptsächlich aus Klassendefinitionen und anderen Elemente verfügbar machen die einzelnen Typeinfo-Elemente, die vom `ITypeLib:GetTypeInfo`. In diesem Abschnitt wird jede Typinformation aus der Typbibliothek im Header in einem Format wiedergegeben, das von den `TYPEKIND`-Informationen abhängt.  
  
- Definition der optionalen GUID im alten Format: Enthält Initialisierungen der benannten GUID-Konstanten. Hierbei handelt es sich um Namen im Format `CLSID_CoClass` und `IID_Interface`, vergleichbar mit denen vom MIDL-Compiler generiert.  
  
- `#include`-Anweisung für den sekundären Header der Typbibliothek.  
  
- Textbaustein für Footer: Schließt aktuell `#pragma pack(pop)` ein.  
  
Alle Bereiche, außer den Codebausteinen und Fußzeile Codebausteine Kopfzeilenbereich, in einem Namespace eingeschlossen sind, mit dem Namen gemäß der `library` -Anweisung in der ursprünglichen IDL-Datei. Sie können die Namen des Typbibliotheksheaders entweder über eine explizite Qualifizierung mit dem Namespacenamen verwenden oder indem Sie die Anweisung  
  
```  
using namespace MyLib;  
```  
  
unmittelbar nach der **#import** -Anweisung im Quellcode.  
  
Der Namespace kann unterdrückt werden, mithilfe der [No_namespace](#_predir_no_namespace) Attribut der **#import** Richtlinie. Allerdings kann das Unterdrücken des Namespace zu Namenskonflikten führen. Der Namespace kann auch umbenannt werden, durch die [Rename_namespace](#_predir_rename_namespace) Attribut.  
  
Der Compiler stellt den vollständigen Pfad zu einer beliebigen Typbibliotheksabhängigkeit bereit, die von der Typbibliothek benötigt wird, die gerade verarbeitet wird. Der Pfad wird in Form von Kommentaren in den Header der Typbibliothek (.TLH) geschrieben, den der Compiler für jede verarbeitete Typbibliothek erstellt.  
  
Wenn eine Typbibliothek Verweise auf Typen enthält, die in anderen Typbibliotheken definiert sind, dann enthält die TLH-Datei Kommentare folgender Art:  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
Der eigentliche Dateiname in der **#import** Kommentar ist der vollständige Pfad der übergreifenden Typbibliothek, wie in der Registrierung gespeichert. Wenn Fehler aufgrund fehlender Typdefinitionen auftreten, überprüfen Sie die Kommentare am Anfang der TLH-Datei, um festzustellen, welche abhängigen Typbibliotheken möglicherweise zuerst importiert werden müssen. Wahrscheinliche Fehler sind Syntaxfehler (z. B. C2143, C2146, C2321), C2501 (fehlende decl-Spezifizierer) oder C2433 ("inline" bei Datendeklaration nicht zulässig) beim Kompilieren der TLI-Datei.  
  
Müssen Sie bestimmen, welche der Kommentare sind nicht anderweitig bereitgestellt von Systemheadern ist, und geben Sie dann eine **#import** -Direktive an einem Punkt vor der **#import** -Direktive des abhängigen Elements der Typbibliothek die Fehler zu beheben.  

##  <a name="_predir_the_23import_directive_import_attributes"></a> #import-Attribute

**#import** kann optional ein oder mehrere Attribute enthalten. Diese Attribute weisen den Compiler an, den Inhalt der Typbibliotheksheader zu ändern. Ein umgekehrter Schrägstrich (**\\**) Symbol kann verwendet werden, um zusätzliche Zeilen in einer einzelnen enthalten **#import** Anweisung. Zum Beispiel:  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
Weitere Informationen finden Sie unter [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md).  
  
**Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)<br/>
[COM-Unterstützung des Compilers](../cpp/compiler-com-support.md)