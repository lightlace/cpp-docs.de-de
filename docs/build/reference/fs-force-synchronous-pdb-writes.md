---
title: /FS (Erzwingen synchroner PDB-Schreibvorgänge)
ms.date: 11/04/2016
f1_keywords:
- /FS
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
ms.openlocfilehash: 97ffb9529087329cf327ba704523b93d5d9b99b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270978"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (Erzwingen synchroner PDB-Schreibvorgänge)

Erzwingt, dass Schreibvorgänge, die Programmdatenbankdatei (PDB) – von erstellten ["/ Zi"](z7-zi-zi-debug-information-format.md) oder ["/ Zi"](z7-zi-zi-debug-information-format.md)– über MSPDBSRV serialisiert werden soll. EXE-DATEI.

## <a name="syntax"></a>Syntax

```
/FS
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung beim **"/ Zi"** oder **"/ Zi"** angegeben ist, wird der Compiler sperrt PDB-Dateien, um Typinformationen und symbolische Debuginformationen zu schreiben. Dadurch kann der Compiler bei einer großen Anzahl von Typen die Typinformationen erheblich schneller generieren. Wenn ein anderer Prozess, beispielsweise ein Antivirenprogramm, die PDB Datei vorübergehend sperrt, können Schreibvorgänge des Compiler möglicherweise nicht ausgeführt werden, sodass ein schwerer Fehler auftritt. Dieses Problem kann auch auftreten, wenn mehrere Kopien von cl.exe auf dieselbe PDB Datei zugreifen. Das kann der Fall sein, wenn die Projektmappe unabhängige Projekte enthält, welche die gleichen Zwischenverzeichnisse oder Ausgabeverzeichnisse verwenden, während parallele Builds aktiviert sind. Die **/FS** -Compileroption verhindert, dass der Compiler die PDB-Datei zu sperren und erzwingt, dass Schreibvorgänge MSPDBSRV durchlaufen. EXE-Datei, die Zugriff serialisiert. Dadurch werden aber nicht alle Fehler verhindert, die auftreten können, wenn mehrere Instanzen von cl.exe gleichzeitig auf die PDB-Datei zugreifen, und zudem dauern Builds erheblich länger. Es empfiehlt sich, die Projektmappe so zu ändern, dass unabhängige Projekte in getrennte Zwischen- und Ausgabeorte schreiben, oder eines der Projekte von den anderen abhängig zu machen, um serialisierte Projekt-Builds zu erzwingen.

Die [/MP](mp-build-with-multiple-processes.md) -Option aktiviert **/FS** standardmäßig.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **C/C++-** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen `/FS` und wählen Sie dann **OK**.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
