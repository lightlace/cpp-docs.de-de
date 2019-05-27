---
title: /DEBUG (Debuginfo generieren)
ms.date: 05/16/2019
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
ms.openlocfilehash: 2ec466a6356ace437d32eb517bf2da291938f5db
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837143"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Debuginfo generieren)

```
/DEBUG[:{FASTLINK|FULL|NONE}]
```

## <a name="remarks"></a>Anmerkungen

Die Option **/DEBUG** erstellt Debuginformationen für die ausführbare Datei.

Der Linker fügt die Debuginformationen in eine Programmdatenbankdatei (PDB) ein. Er aktualisiert die PDB während nachfolgender Builds des Programms.

Eine zum Debuggen erstellte ausführbare Datei (EXE oder DLL) enthält den Namen und Pfad der zugeordneten PDB. Der Debugger liest den eingebetteten Namen und verwendet die PDB, wenn Sie das Programm debuggen. Der Linker verwendet den Basisnamen des Programms und die Erweiterung PDB für die Benennung der Programmdatenbank und bettet den Pfad ein, wo er erstellt wurde. Um dieses Standardverhalten außer Kraft zu setzen, legen Sie [/PDB](pdb-use-program-database.md) fest, und geben Sie einen anderen Dateinamen an.

Die Option **/DEBUG:FASTLINK** ist in Visual Studio 2017 und höher verfügbar. Diese Option belässt private Symbolinformationen in den einzelnen Kompilierungsprodukten, die zum Erstellen der ausführbaren Datei verwendet werden. Sie generiert eine eingeschränkte PDB, die in die Debuginformationen in den Objektdateien und Bibliotheken, die zum Erstellen der ausführbaren Datei verwendet werden, hinein indiziert, statt eine vollständige Kopie zu erstellen. Mit dieser Option kann das Linken zwei bis vier Mal so schnell wie bei einer vollständigen PDB-Generierung erfolgen, daher wird sie empfohlen, wenn Sie lokal debuggen und Ihnen die Buildprodukte zur Verfügung stehen. Diese eingeschränkte PDB kann nicht zum Debuggen verwendet werden, wenn die erforderlichen Buildprodukte nicht verfügbar sind, etwa wenn die ausführbare Datei auf einem anderen Computer bereitgestellt wird. An einer Entwicklereingabeaufforderung können Sie das Tool „mspdbcmf.exe“ verwenden, um aus dieser eingeschränkten PDB eine vollständige PDB zu generieren. Verwenden Sie in Visual Studio die Menüelemente „Projekt“ oder „Build“, um eine vollständige PDB-Datei für das Projekt oder die Projektmappe zu generieren.

Die Option **/DEBUG:FULL** verschiebt alle privaten Symbolinformationen aus den einzelnen Kompilierungsprodukten (Objektdateien und Bibliotheken) in eine einzelne PDB. Dies kann der zeitaufwändigste Teil des Linkvorgangs sein. Allerdings kann die vollständige PDB verwendet werden, um die ausführbare Datei zu debuggen, wenn keine anderen Buildprodukte verfügbar sind, etwa wenn die ausführbare Datei bereitgestellt wird.

Bei der Option **/DEBUG:NONE** wird keine PDB erstellt.

Wenn Sie **/DEBUG** ohne ergänzende Optionen angeben, ist der Standardwert des Linkers bei Builds von der Befehlszeile oder mit Makefile, für Releasebuilds in der Visual Studio-IDE und sowohl für Debug- als auch für Releasebuilds in Visual Studio 2015 und früheren Versionen **/DEBUG:FULL**. Seit Visual Studio 2017 ist der Standardwert des Buildsystems in der IDE **/DEBUG:FASTLINK**, wenn für Debugbuilds die Option **/DEBUG** angegeben wird. Andere Standardwerte bleiben unverändert, um die Abwärtskompatibilität zu gewährleisten.

Die [C7-Kompatibel](z7-zi-zi-debug-information-format.md)-Option (/Z7) des Compilers veranlasst den Compiler, die Debuginformationen in den OBJ-Datei zu belassen. Sie können auch die Compileroption [Programmdatenbank](z7-zi-zi-debug-information-format.md) (/Zi) verwenden, um die Debuginformationen einer PDB für die OBJ-Datei zu speichern. Der Linker sucht zuerst unter dem absoluten Pfad, der in der OBJ-Datei eingetragen ist, nach der PDB des Objekts und anschließend im Verzeichnis, das die OBJ-Datei enthält. Sie können dem Linker weder den Namen noch den Speicherort der PDB-Datei eines Objekts angeben.

[/INCREMENTAL](incremental-link-incrementally.md) ist bei der Angabe von /DEBUG impliziert.

/DEBUG ändert die Standardwerte für die Option [/OPT](opt-optimizations.md) von REF in NOREF und von ICF in NOICF, wenn Sie also die ursprünglichen Standardwerte verwenden möchten, müssen Sie explizit /OPT:REF oder /OPT:ICF angeben.

Es ist nicht möglich, eine EXE- oder DLL-Datei zu erstellen, die Debuginformationen enthält. Die Debuginformationen werden immer in einer OBJ- oder PDB-Datei platziert.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf den Ordner **Linker**.

1. Klicken Sie auf die Eigenschaftenseite **Debuggen**.

1. Ändern Sie das Attribut **Debuginfo generieren**, um die PDB-Generierung zu aktivieren. Dadurch wird in Visual Studio 2017 und höher standardmäßig /DEBUG:FASTLINK aktiviert.

1. Ändern Sie die Eigenschaft **Vollständige Programmdatenbankdatei erstellen**, um für jeden inkrementellen Build für die Generierung vollständiger PDB-Dateien /DEBUG:FULL zu aktivieren.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
