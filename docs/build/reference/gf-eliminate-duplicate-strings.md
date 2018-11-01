---
title: /GF (Doppelte Zeichenfolgen beseitigen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: 7504c12584d931b0f39062f393765ad8124fc0dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561552"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Doppelte Zeichenfolgen beseitigen)

Kann der Compiler eine einzige Kopie identischer Zeichenfolgen im Programmimage und im Speicher während der Ausführung zu erstellen. Dies ist eine Optimierung namens *Stringpooling* kleinere Programme erstellen können.

## <a name="syntax"></a>Syntax

```
/GF
```

## <a name="remarks"></a>Hinweise

Bei Verwendung von **/GF**, das Betriebssystem wird die Zeichenfolgenteil des Arbeitsspeichers nicht ausgetauscht, und erhalten die Zeichenfolgen aus der Imagedatei sichern.

**/ GF** Zeichenfolgen als nur-Lese pools. Wenn Sie versuchen, die Zeichenfolgen unter Ändern **/GF**, ein Fehler auftritt.

Stringpooling ermöglicht es, was als mehrere Verweise auf mehrere Puffer werden mehrere Verweise auf einen einzelnen Puffer vorgesehen war. In den folgenden Code `s` und `t` mit derselben Zeichenfolge initialisiert werden. Stringpooling bewirkt, dass sie auf den gleichen Speicher zu verweisen:

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
>  Die ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) -Option zum Bearbeiten und fortfahren, setzt automatisch das **/GF** Option.

> [!NOTE]
>  Die **/GF** Compileroption erstellt einen adressierbaren Abschnitt für jede eindeutige Zeichenfolge. Und in der Standardeinstellung kann eine Objektdatei bis zu 65.536 adressierbare Abschnitte enthalten. Wenn Ihr Programm mehr als 65.536 Zeichenfolgen enthält, verwenden Sie die [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) -Compileroption verwenden, um mehr Abschnitte zu erstellen.

**/ GF** ist gültig, wenn ["/ O1"](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder **"/ O2"** verwendet wird.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Stringpooling aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)