---
title: -Volatile (Interpretation des volatile-Schlüsselwort) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
dev_langs:
- C++
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccd36c5edaaab8577e5f278b25b51ce69e0633f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378196"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (Interpretation des volatile-Schlüsselworts)

Gibt an, wie die [volatile](../../cpp/volatile-cpp.md) Schlüsselwort ist, interpretiert werden sollen.

## <a name="syntax"></a>Syntax

> **/ volatile:**{**Iso**|**ms**}  

## <a name="arguments"></a>Argumente

**/volatile:ISO**  
Wählt strenge `volatile`-Semantik aus, wie vom ISO-Standard für die C++-Sprache definiert. Semantiken zum Abrufen bzw. Freigeben sind bei flüchtigen Zugriffen nicht garantiert. Wenn der Compiler auf ARM ausgerichtet ist, ist dies die Standardinterpretation von `volatile`.

**/volatile:ms**  
Wählt erweiterte Microsoft-`volatile`-Semantik aus, mit der über den ISO-Standard für die C++-Sprache hinausgehe Speicheranordnungsgarantien hinzufügt werden. Semantiken zum Abrufen bzw. Freigeben sind bei flüchtigen Zugriffen garantiert. Allerdings zwingt diese Option den Compiler auch zum Generieren von Hardwarearbeitsspeicherbarrieren, die möglicherweise beträchtlichen Mehraufwand für ARM und andere schwache Speicheranordnungsarchitekturen bedeuten. Wenn der Compiler auf eine Plattform außer ARM ausgerichtet ist, ist dies die Standardinterpretation von `volatile`.

## <a name="remarks"></a>Hinweise

Es wird dringend empfohlen, dass Sie verwenden **/volatile:iso** zusammen mit expliziten Synchronisierungsprimitiven und systeminterne Compilerfunktionen, wenn Sie mit Arbeitsspeicher arbeiten, der über Threads freigegeben wird. Weitere Informationen finden Sie unter [volatile](../../cpp/volatile-cpp.md).

Wenn Sie vorhandenen Code portieren oder diese Option mitten in einem Projekt ändern, ist es möglicherweise hilfreich, Warnung aktivieren [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) um codespeicherorte zu identifizieren, die nach den Unterschieden in der Semantik betroffen sind.

Es gibt keine `#pragma`-Entsprechung, zum Steuern dieser Option.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>So legen Sie die /volatile-Compileroption in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. In der **Zusatzoptionen** fügen **/volatile:iso** oder **/volatile:ms** und wählen Sie dann **OK** oder **übernehmen** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[volatile](../../cpp/volatile-cpp.md)  
[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
