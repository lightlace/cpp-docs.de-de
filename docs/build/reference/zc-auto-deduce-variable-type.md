---
title: /Zc:auto (Variablentyp ableiten)
ms.date: 02/28/2018
f1_keywords:
- /Zc:auto
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
ms.openlocfilehash: 9609bc484310fbc9999182add384eb4e438378bf
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446246"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (Variablentyp ableiten)

Die **/Zc: Auto [-]** Compiler-Option weist den Compiler mit, wie Sie mit der [auto-Schlüsselwort](../../cpp/auto-keyword.md) zum Deklarieren von Variablen. Wenn Sie angeben, dass die Standardoption, **/Zc: Auto**, leitet der Compiler den Typ der deklarierten Variable vom entsprechenden Initialisierungsausdruck. Bei Angabe von **/Zc:auto-**, weist der Compiler die Variable der automatischen Speicherklasse.

## <a name="syntax"></a>Syntax

> **/Zc:auto**[**-**]

## <a name="remarks"></a>Hinweise

Der C++-Standard definiert eine ursprüngliche und eine überarbeitete Bedeutung für das `auto`-Schlüsselwort. Vor Visual Studio 2010 wird das Schlüsselwort eine Variable in der automatischen Speicherklasse deklariert; d. h. eine Variable, die eine lokale Lebensdauer hat. Ab Visual Studio 2010, leitet das Schlüsselwort den Typ einer Variable vom Initialisierungsausdruck der Deklaration ab. Verwenden Sie die **/Zc: Auto [-]** -Compileroption verwenden, um den Compiler anweist, verwenden Sie die ursprüngliche oder überarbeitete Bedeutung des das `auto` Schlüsselwort. Die **/Zc: Auto** Option ist standardmäßig aktiviert. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option ändert nicht die Standardeinstellung von **/Zc: Auto**.

Der Compiler gibt eine entsprechende diagnosemeldung aus, wenn die Verwendung von der `auto` Schlüsselwort widerspricht der aktuellen **/Zc: Auto** -Compileroption. Weitere Informationen finden Sie unter [auto-Schlüsselwort](../../cpp/auto-keyword.md). Weitere Informationen über Konformitätsprobleme mit Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen **/Zc: Auto** oder **/Zc:auto-** auf die **zusätzliche Optionen:** Bereich.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
[Auto-Schlüsselwort](../../cpp/auto-keyword.md)
