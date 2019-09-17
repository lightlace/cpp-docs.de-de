---
title: '##import-Anweisung (C++)'
ms.date: 08/29/2019
f1_keywords:
- '#import'
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
ms.openlocfilehash: afd05e7380ec3838fe9763be23ccfae338adb4fb
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220260"
---
# <a name="import-directive-c"></a>#Import-Direktive (C++)

**C++Zugeschnitten**

Wird verwendet, um Informationen aus einer Typbibliothek zu integrieren. Der Inhalt der Typbibliothek wird in C++-Klassen konvertiert, die größtenteils die COM-Schnittstellen beschreiben.

## <a name="syntax"></a>Syntax

> **#Import** "*filename*" \[- *Attribute*] \
> **#Import** \<filename-> Attribute]\[

### <a name="parameters"></a>Parameter

*Einfügen*\
Gibt die zu importierende Typbibliothek an. Der *Dateiname* kann eine der folgenden Arten sein:

- Der Name einer Datei, die eine Typbibliothek enthält, z. B. eine OLB-, TLB- oder DLL-Datei. Das Schlüsselwort `file:`,, kann jedem Dateinamen vorangestellt werden.

- Die ProgID eines Steuerelements in der Typbibliothek. Das Schlüsselwort `progid:`,, kann jeder ProgID vorangestellt werden. Beispiel:

    ```cpp
    #import "progid:my.prog.id.1.5"
    ```

   Weitere Informationen zu ProgIDs finden Sie unter [angeben der Lokalisierungs-ID und der Versionsnummer](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber).

   Wenn Sie einen 32-Bit-Cross-Compiler für ein 64-Bit-Betriebssystem verwenden, kann der Compiler nur die 32-Bit-Registrierungs Struktur lesen. Sie sollten den systemeigenen 64-Bit-Compiler verwenden, um eine 64-Bit-Typbibliothek zu erstellen und zu registrieren.

- Die Bibliotheks-ID der Typbibliothek. Das Schlüsselwort `libid:`,, kann jeder Bibliotheks-ID vorangestellt werden. Beispiel:

    ```cpp
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")
    ```

   Wenn Sie `version` oder `lcid` nicht angeben, werden die auf `progid:` angewendeten [Regeln](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) auch auf `libid:` angewendet.

- Ein ausführbare Datei (EXE-Datei).

- Eine Bibliotheksdatei (DLL-Datei), die eine Typbibliotheks Ressource (z. b. eine. ocx) enthält.

- Ein Verbunddokument, das eine Typbibliothek enthält.

- Alle anderen Dateiformate, die von der **LoadTypeLib** -API verstanden werden können.

*legt*\
Ein oder mehrere [#Import Attribute](#_predir_the_23import_directive_import_attributes). Trennen Sie Attribute entweder mit einem Komma oder einem Leerzeichen. Beispiel:

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only
```

\- oder -

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only
```

## <a name="remarks"></a>Hinweise

### <a name="_predir_the_23import_directive_searchorderforfilename"></a>Such Reihenfolge für Dateinamen

der *Dateiname* ist optional eine Verzeichnis Spezifikation vorangestellt. Der Dateiname muss eine vorhandene Datei benennen. Der Unterschied zwischen den beiden Syntaxformen liegt in der Reihenfolge, in der der Präprozessor nach den Typbibliotheksdateien sucht, wenn der Pfad unvollständig angegeben wird.

|Syntaxformat|Aktion|
|-----------------|------------|
|Format mit Anführungszeichen|Weist den Präprozessor an, nach Typbibliotheks Dateien zuerst im Verzeichnis der Datei zu suchen, die die **#Import** -Anweisung enthält, und dann in den Verzeichnissen aller Dateien, die`#include`() diese Datei enthalten. Der Präprozessor sucht dann in den unten aufgeführten Verzeichnissen.|
|Format mit spitzer Klammer|Weist den Präprozessor an, nach Typbibliotheksdateien in den folgenden Verzeichnissen zu suchen:<br /><br /> 1.  Die `PATH` Liste der Umgebungsvariablen Pfade<br />2.  Die `LIB` Liste der Umgebungsvariablen Pfade<br />3.  Der von der [/I](../build/reference/i-additional-include-directories.md) -Compileroption angegebene Pfad, mit dem Unterschied, dass der Compiler nach einer Typbibliothek sucht, auf die von einer anderen Typbibliothek mit dem [no_registry](../preprocessor/no-registry.md) -Attribut verwiesen wurde.|

### <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a>Angeben der Lokalisierungs-ID und der Versionsnummer

Wenn Sie eine ProgID angeben, können Sie auch die Lokalisierungs-ID und die Versionsnummer der ProgID angeben. Beispiel:

```cpp
#import "progid:my.prog.id" lcid("0") version("4.0)
```

Wenn Sie keine Lokalisierungs-ID angeben, wird eine ProgID gemäß den folgenden Regeln ausgewählt:

- Wenn nur eine Lokalisierungs-ID vorhanden ist, wird diese verwendet.

- Wenn mehr als eine Lokalisierungs-ID vorhanden ist, wird die erste mit der Versionsnummer 0, 9 oder 409 verwendet.

- Wenn mehr als eine Lokalisierungs-ID vorhanden ist und keines der Werte 0, 9 oder 409 ist, wird der letzte verwendet.

- Wenn Sie keine Versionsnummer angeben, wird die neueste Version verwendet.

###  <a name="_predir_the_23import_directive_header_files_created_by_import"></a>Durch den Import erstellte Header Dateien

**#Import** erstellt zwei Header Dateien, die den Inhalt der Typbibliothek C++ im Quellcode rekonstruieren. Die primäre Header Datei ähnelt der Datei, die vom Microsoft Interface Definition Language-Compiler (mittlerer l) erstellt wurde, aber mit zusätzlichem vom Compiler generierten Code und Daten. Die [primäre Header Datei](#_predir_the_primary_type_library_header_file) hat denselben Basis Namen wie die Typbibliothek und eine. TLH-Erweiterung. Die sekundäre Headerdatei weist den gleichen Basisnamen wie die Typbibliothek auf, mit einer TLI-Erweiterung. Sie enthält die Implementierungen für vom Compiler generierte Memberfunktionen und wird in die primäre Headerdatei eingefügt (`#include`).

Wenn Sie eine dispinterface-Eigenschaft importieren `byref` , die Parameter verwendet, generiert **#Import** keine [__declspec (Property)](../cpp/property-cpp.md) -Anweisung für die Funktion.

Beide Header Dateien werden in das Ausgabeverzeichnis eingefügt, das von der [/FO (Name Object File)](../build/reference/fo-object-file-name.md) -Option angegeben wird. Sie werden dann vom Compiler gelesen und kompiliert, als wäre die primäre Header Datei durch eine `#include` -Direktive benannt.

Die folgenden Compileroptimierungen sind in der **#Import** -Direktive enthalten:

- Wenn sie erstellt wird, wird der Headerdatei der gleiche Zeitstempel gegeben wie der Typbibliothek.

- Wenn **#Import** verarbeitet wird, prüft der Compiler zunächst, ob der Header vorhanden und aktuell ist. Wenn ja, muss es nicht neu erstellt werden.

Die **#Import** -Direktive ist auch an minimaler Neuerstellung beteiligt und kann in eine vorkompilierte Header Datei eingefügt werden.  Weitere Informationen finden Sie unter [Erstellen vorkompilierter Header Dateien](../build/creating-precompiled-header-files.md).

### <a name="_predir_the_primary_type_library_header_file"></a>Header Datei der primären Typbibliothek

Die primäre Headerdatei der Typbibliothek umfasst sieben Abschnitte:

- Überschrift Bausteine: Besteht aus Kommentaren, `#include` -Anweisung für comdef. H (das einige Standard Makros definiert, die im-Header verwendet werden) und andere Informationen zum Setup.

- Forward-Verweise und Typedefs: Besteht aus Struktur Deklarationen wie `struct IMyInterface` und Typedefs.

- Intelligente Zeiger Deklarationen: Die Vorlagen Klasse `_com_ptr_t` ist ein intelligenter Zeiger. Es kapselt Schnittstellen Zeiger und entfällt, dass die-, `AddRef` `Release`-und- `QueryInterface` Funktionen aufgerufen werden müssen. Außerdem wird der `CoCreateInstance` -Befehl ausgeblendet, wenn ein neues COM-Objekt erstellt wird. In diesem Abschnitt wird die Macro `_COM_SMARTPTR_TYPEDEF` -Anweisung verwendet, um Typedefs von COM-Schnittstellen als Vorlagen Spezialisierungs der [_com_ptr_t](../cpp/com-ptr-t-class.md) -Vorlagen Klasse festzulegen. Beispielsweise ist für die `IMyInterface`-Schnittstelle der. Die TLH-Datei enthält Folgendes:

    ```TLH
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
    ```

   Dies wird vom Compiler zu Folgendem erweitert:

    ```cpp
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;
    ```

   Typ `IMyInterfacePtr` kann dann anstelle des nicht formatierten Schnittstellenzeigers `IMyInterface*` verwendet werden. Folglich ist es nicht erforderlich, die verschiedenen `IUnknown` Element Funktionen aufzurufen.

- Typeingabe-Deklarationen: Besteht primär aus Klassendefinitionen und anderen Elementen, die die einzelnen von `ITypeLib:GetTypeInfo`zurückgegebenen typeinzelfo-Elemente verfügbar machen. In diesem Abschnitt wird jede Typinformation aus der Typbibliothek im Header in einem Format wiedergegeben, das von den `TYPEKIND`-Informationen abhängt.

- Optionale GUID-Definition im alten Stil: Enthält Initialisierungen der benannten GUID-Konstanten. Diese Namen haben das `CLSID_CoClass` Format und, ähnlich wie die, die vom-Mittell- `IID_Interface`Compiler generiert werden.

- `#include`-Anweisung für den sekundären Header der Typbibliothek.

- Footer-Bausteine: Umfasst `#pragma pack(pop)`derzeit.

Alle Abschnitte, außer dem Titel der Überschriften und der Fußzeile, sind in einem Namespace mit dem Namen eingeschlossen, der durch die `library` -Anweisung in der ursprünglichen IDL-Datei angegeben wird. Mit dem Namespace Namen können Sie die Namen aus dem Header der Typbibliothek mit einer expliziten Qualifikation verwenden. Oder Sie können die folgende Anweisung einschließen:

```cpp
using namespace MyLib;
```

unmittelbar nach der **#Import** -Anweisung im Quellcode.

Der Namespace kann mithilfe des [no_namespace](no-namespace.md))-Attributs der **#Import** -Direktive unterdrückt werden. Allerdings kann das Unterdrücken des Namespace zu Namenskonflikten führen. Der Namespace kann auch durch das [rename_namespace](rename-namespace.md) -Attribut umbenannt werden.

Der Compiler stellt den vollständigen Pfad zu jeder Typbibliotheks Abhängigkeit bereit, die von der zurzeit verarbeiteten Typbibliothek benötigt wird. Der Pfad wird in Form von Kommentaren in den Header der Typbibliothek (.TLH) geschrieben, den der Compiler für jede verarbeitete Typbibliothek erstellt.

Wenn eine Typbibliothek Verweise auf Typen enthält, die in anderen Typbibliotheken definiert sind, dann enthält die TLH-Datei Kommentare folgender Art:

```TLH
//
// Cross-referenced type libraries:
//
//  #import "c:\path\typelib0.tlb"
//
```

Der tatsächliche Dateiname im **#Import** Kommentar ist der vollständige Pfad der quer referenzierten Typbibliothek, wie er in der Registrierung gespeichert ist. Wenn Fehler aufgrund fehlender Typdefinitionen auftreten, überprüfen Sie die Kommentare am Anfang von. TLH, um anzuzeigen, welche abhängigen Typbibliotheken möglicherweise zuerst importiert werden müssen. Wahrscheinliche Fehler sind Syntaxfehler (z. B. C2143, C2146, C2321), C2501 (fehlende decl-Spezifizierer) oder C2433 ("inline" bei Datendeklaration nicht zulässig) beim Kompilieren der TLI-Datei.

Um Abhängigkeitsfehler zu beheben, bestimmen Sie, welche der Abhängigkeits Kommentare von Systemheadern nicht anderweitig bereitgestellt werden, und stellen Sie dann eine **#Import** -Direktive zu einem bestimmten Zeitpunkt vor der **#Import** -Direktive der abhängigen Typbibliothek bereit.

### <a name="_predir_the_23import_directive_import_attributes"></a>#Import Attribute

**#Import** können optional ein oder mehrere Attribute einschließen. Diese Attribute weisen den Compiler an, den Inhalt der Typbibliotheksheader zu ändern. Ein umgekehrter schräg **\\** Strich () kann verwendet werden, um zusätzliche Zeilen in eine einzelne **#Import** Anweisung aufzunehmen. Beispiel:

```cpp
#import "test.lib" no_namespace \
   rename("OldName", "NewName")
```

Weitere Informationen finden Sie unter [#Import Attribute](../preprocessor/hash-import-attributes-cpp.md).

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[Präprozessordirektiven](../preprocessor/preprocessor-directives.md)\
[Compilerunterstützung](../cpp/compiler-com-support.md)
