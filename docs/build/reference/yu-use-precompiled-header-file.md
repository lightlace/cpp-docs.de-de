---
title: /Yu (Vorkompilierte Headerdatei verwenden)
ms.date: 11/04/2016
f1_keywords:
- /yu
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
ms.openlocfilehash: 8d2b02c378179ac2603ec095efe89ce78f9f1afa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505341"
---
# <a name="yu-use-precompiled-header-file"></a>/Yu (Vorkompilierte Headerdatei verwenden)

Weist den Compiler auf eine vorhandene Datei der vorkompilierten Headerdatei (.pch) in der aktuellen Kompilierung verwenden.

## <a name="syntax"></a>Syntax

```
/Yu[filename]
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Der Name einer Headerdatei, die in der Quelldatei über enthalten ist ein **#include** Präprozessordirektive angegeben.

## <a name="remarks"></a>Hinweise

Der Namen der Includedatei muss sowohl für die **"/ Yc"** Option, der vorkompilierte Header und alle erstellt, nachfolgenden **"/ Yu"** Option, der angibt, mit der vorkompilierten Headerdatei.

Für **"/ Yc"**, `filename` gibt an, den Zeitpunkt der Vorkompilierung beendet; der Compiler kompiliert den gesamten Code bis einschließlich `filename` und den daraus resultierende vorkompilierten Header mit dem Basisnamen der Include-Datei und die Erweiterung PCH.

Die PCH-Datei muss erstellt worden mit **"/ Yc"**.

Der Compiler behandelt alle Code vor der h-Datei als vorkompiliert. Er überspringt diesen bis hinter das **#include** der h-Datei zugeordnete Richtlinie verwendet der Code in die PCH-Datei enthalten sind, und klicken Sie dann kompiliert alle Code nach `filename`.

In der Befehlszeile darf kein Leerzeichen zwischen **"/ Yu"** und `filename`.

Bei Angabe der **"/ Yu"** Option ohne einen Dateinamen ein, die Quellcode-Verwaltungsprogramm darf eine [#pragma Hdrstop](../../preprocessor/hdrstop.md) Pragma, das den Dateinamen der vorkompilierten Headerdatei, PCH-Datei angibt. In diesem Fall verwendet der Compiler die vorkompilierte Headerdatei (PCH-Datei) von  [ /fp (Name. PCH-Datei)](../../build/reference/fp-name-dot-pch-file.md). Der Compiler auf den Speicherort der diesem Pragma wird übersprungen, wird von der kompilierte Zustand aus der vorkompilierten Header-Datei, die durch das Pragma angegeben und kompiliert anschließend nur Code, der dem Pragma folgt. Wenn **#pragma Hdrstop** gibt keinen Dateinamen ein, der Compiler sucht nach einer Datei mit einem Namen, die von der Basisname der Quelldatei mit einer .pch-Erweiterung abgeleitet. Sie können auch die **/fp** Option aus, um eine andere PCH-Datei angeben.

Bei Angabe der **"/ Yu"** option ohne einen Dateinamen und Angeben einer **Hdrstop** Pragma, wird eine Fehlermeldung generiert und die Kompilierung schlägt fehl.

Wenn die **"/ Yc"** `filename` und **"/ Yu"** `filename` Optionen zu vorkommen, in der gleichen Befehlszeile und den gleichen Dateinamen Verweisdaten **"/ Yc"** `filename` akzeptiert Vorrang bei der Vorkompilierung alle Codes bis einschließlich der benannten Datei. Diese Funktion vereinfacht das Schreiben von Makefiles.

Da PCH-Dateien mit Informationen über die computerumgebung sowie die Arbeitsspeicher-Adressinformationen über das Programm enthält, sollten Sie nur eine Pch-Datei auf dem Computer verwenden, der es erstellt wurde.

Weitere Informationen zu vorkompilierten Headern finden Sie unter:

- [/Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)

- [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Geben Sie ["/ Yc" (Erstellen vorkompilierter Headerdatei)](../../build/reference/yc-create-precompiled-header-file.md) für eine CPP-Datei in Ihrem Projekt.

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **vorkompilierte Header** Eigenschaftenseite.

1. Ändern der **PCH durch Datei erstellen/verwenden** Eigenschaft oder das **vorkompilierten Header erstellen/verwenden** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.

## <a name="examples"></a>Beispiele

Wenn der folgende Code:

```
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
...
```

wird mit der Befehlszeile kompiliert `CL /YuMYAPP.H PROG.CPP`, verarbeitet der Compiler nicht die drei Anweisungen jedoch Code verwendet, die vorkompilierte MYAPP.pch, wodurch spart die Zeit, die bei der vorverarbeitung alle drei Dateien (und alle Dateien, die sie möglicherweise enthalten) enthalten.

Sie können die  [ /fp (Name. PCH-Datei)](../../build/reference/fp-name-dot-pch-file.md) -Option mit der **"/ Yu"** der Name der PCH-Datei angeben, wenn der Name entweder der Dateinamenargument für unterscheidet **"/ Yc"** oder der Basisname der Quelldatei, wie in der folgende:

```
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP
```

Dieser Befehl gibt eine vorkompilierte Headerdatei mit dem Namen MYPCH.pch. Der Compiler verwendet seinen Inhalt, um den vorkompilierten Zustand aller Header-Dateien bis zur und einschließlich MYAPP.h wiederherzustellen. Klicken Sie dann kompiliert der Compiler den Code, der auftritt, nachdem die MYAPP.h **enthalten** Anweisung.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)