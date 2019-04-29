---
title: /volatile (Interpretation des volatile-Schlüsselworts)
ms.date: 11/04/2016
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
ms.openlocfilehash: 02871622242930d7419fda16f4d106fccb2056f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316638"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (Interpretation des volatile-Schlüsselworts)

Gibt an, wie die [flüchtige](../../cpp/volatile-cpp.md) Schlüsselwort ist, interpretiert werden soll.

## <a name="syntax"></a>Syntax

> **/ volatile:**{**Iso**|**ms**}

## <a name="arguments"></a>Argumente

**/volatile:iso**<br/>
Wählt strenge `volatile`-Semantik aus, wie vom ISO-Standard für die C++-Sprache definiert. Semantiken zum Abrufen bzw. Freigeben sind bei flüchtigen Zugriffen nicht garantiert. Wenn der Compiler auf ARM ausgerichtet ist, ist dies die Standardinterpretation von `volatile`.

**/volatile:ms**<br/>
Wählt erweiterte Microsoft-`volatile`-Semantik aus, mit der über den ISO-Standard für die C++-Sprache hinausgehe Speicheranordnungsgarantien hinzufügt werden. Semantiken zum Abrufen bzw. Freigeben sind bei flüchtigen Zugriffen garantiert. Allerdings zwingt diese Option den Compiler auch zum Generieren von Hardwarearbeitsspeicherbarrieren, die möglicherweise beträchtlichen Mehraufwand für ARM und andere schwache Speicheranordnungsarchitekturen bedeuten. Wenn der Compiler auf eine Plattform außer ARM ausgerichtet ist, ist dies die Standardinterpretation von `volatile`.

## <a name="remarks"></a>Hinweise

Es wird dringend empfohlen, dass Sie verwenden **/volatile:iso** zusammen mit expliziten Synchronisierungsprimitiven und systeminterne Compilerfunktionen, wenn Sie mit Arbeitsspeicher arbeiten, der threadübergreifend bereitgestellt wird. Weitere Informationen finden Sie unter [flüchtige](../../cpp/volatile-cpp.md).

Wenn Sie vorhandenen Code portieren oder diese Option mitten in einem Projekt ändern, es kann hilfreich sein, aktivieren Sie die Warnung [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) Codepositionen zu identifizieren, die den Unterschied in der Semantik betroffen sind.

Es gibt keine `#pragma`-Entsprechung, zum Steuern dieser Option.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>So legen Sie die /volatile-Compileroption in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. In der **zusätzliche Optionen** fügen **/volatile:iso** oder **angegebenem** und wählen Sie dann **OK** oder **übernehmen** zum Speichern der Änderungen.

## <a name="see-also"></a>Siehe auch

[volatile](../../cpp/volatile-cpp.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
