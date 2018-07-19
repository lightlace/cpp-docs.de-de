---
title: '-Zc: Auto (Variablentyp ableiten) | Microsoft Docs'
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:auto
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caa64f64b75145c850c6f6393570dc3f9ba0b0d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379574"
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (Variablentyp ableiten)

Die **/Zc: Auto [-]** Compileroption teilt dem Compiler mit, wie Sie die [auto-Schlüsselwort](../../cpp/auto-keyword.md) um Variablen zu deklarieren. Wenn Sie die Standardoption angeben **/Zc: Auto**, leitet der Compiler den Typ der deklarierten Variable vom entsprechenden Initialisierungsausdruck. Bei Angabe von **/Zc:auto-**, ordnet der Compiler die Variable der automatischen Speicherklasse.

## <a name="syntax"></a>Syntax

> **/Zc:auto**[**-**]  

## <a name="remarks"></a>Hinweise

Der C++-Standard definiert eine ursprüngliche und eine überarbeitete Bedeutung für das `auto`-Schlüsselwort. Vor dem [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], das-Schlüsselwort deklariert eine Variable in der automatischen Speicherklasse, d. h. eine Variable, die verfügt über eine lokalen Lebensdauer. Beginnend mit [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], das Schlüsselwort leitet den Typ einer Variablen aus der Deklaration Initialisierungsausdruck. Verwenden Sie die **/Zc: Auto [-]** Compileroption, um den Compiler aufzufordern, verwenden Sie die ursprünglichen oder überarbeitete Bedeutung von der `auto` Schlüsselwort. Die **/Zc: Auto** Option ist standardmäßig aktiviert. Die [/ liberalen-](permissive-standards-conformance.md) Option ändert nicht die Standardeinstellung von **/Zc: Auto**.

Der Compiler gibt eine entsprechende diagnosemeldung aus, wenn die Verwendung der `auto` Schlüsselwort widerspricht den aktuellen **/Zc: Auto** -Compileroption. Weitere Informationen finden Sie unter [auto-Schlüsselwort](../../cpp/auto-keyword.md). Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen **/Zc: Auto** oder **/Zc:auto-** auf die **zusätzliche Optionen:** Bereich.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[Auto-Schlüsselwort](../../cpp/auto-keyword.md)
