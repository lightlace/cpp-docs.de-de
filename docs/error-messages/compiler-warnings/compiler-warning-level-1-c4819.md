---
title: Compilerwarnung (Stufe 1) C4819
ms.date: 11/04/2016
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: c0ca29a304fbd05cb0c6b7d1b06414304c70fb2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596611"
---
# <a name="compiler-warning-level-1-c4819"></a>Compilerwarnung (Stufe 1) C4819

Die Datei enthält ein Zeichen, das in der aktuellen Codepage (Nummer) nicht dargestellt werden kann. Speichern Sie die Datei im Unicode-Format, um Datenverluste zu vermeiden.

C4819 tritt auf, wenn eine ANSI-Quelldatei auf einem System mit einer Codepage kompiliert wird, die nicht alle Zeichen in der Datei darstellen kann.

Um C4819 zu beheben, speichern Sie die Datei im Unicode-Format. Wählen Sie in Visual Studio **Datei**, **Erweiterte Speicheroptionen**. In der **Erweiterte Speicheroptionen** Dialogfeld wählen eine Codierung, die alle Zeichen in der Datei darstellen kann, z. B. UTF-8, und wählen Sie dann **OK**.