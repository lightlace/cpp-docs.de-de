---
title: Compilerwarnung (Stufe 1) C4819
ms.date: 04/08/2019
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: d43b49d473e7113d8cdfb89aaa6e93045e13d0f7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777825"
---
# <a name="compiler-warning-level-1-c4819"></a>Compilerwarnung (Stufe 1) C4819

> Die Datei enthält ein Zeichen, das in der aktuellen Codepage nicht dargestellt werden kann (*Anzahl*). Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden.

C4819 tritt auf, wenn Sie kompilieren eine ANSI-Quelldatei auf einem System mit einer Codepage, die alle Zeichen in der Datei darstellen kann.

Es gibt mehrere Möglichkeiten, um C4819 zu beheben. Eine einfache Möglichkeit ist, um die Beschädigung Zeichen und zu entfernen, wenn Sie ihn, z. B. nicht benötigen, wenn es in einem Kommentar befindet. Sie können die Codepage des Systems in der Systemsteuerung auf einen festlegen, die den Zeichensatz ab, indem Sie Ihren Quellcode unterstützt. Sie können die Unicode verwenden [escape-Zeichensequenzen](/cpp/c-language/escape-sequences) erstellen Zeichen oder Zeichenfolgen, die nur das grundlegende ANSI-Zeichensatz in Ihrem Quellcode. Schließlich können Sie die Datei in einem Unicode-Format mit einer Signatur, auch bekannt als eine Bytereihenfolge-Marke (BOM) speichern.

Wählen Sie zum Speichern einer Datei im Unicode-Format in Visual Studio **Datei** > **speichern**. In der **Datei speichern unter** Dialogfeld wählen die Dropdownliste für die **speichern** und wählen Sie **mit Codierung speichern**. Wenn Sie auf dem gleichen Dateinamen speichern, müssen Sie möglicherweise zu bestätigen, dass Sie die Datei ersetzen möchten. In der **Erweiterte Speicheroptionen** Dialogfeld Wählen Sie eine Codierung, die alle Zeichen in der Datei darstellen kann, z. B. **Unicode (UTF-8 mit Signatur) - Codepage 65001**, und wählen Sie dann  **OK**.