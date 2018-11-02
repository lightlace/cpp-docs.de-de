---
title: Schwerwiegender Fehler C1047
ms.date: 11/04/2016
f1_keywords:
- C1047
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
ms.openlocfilehash: 053c4d828b3583d0e16ab8f4fe03a4b0bbed96f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663183"
---
# <a name="fatal-error-c1047"></a>Schwerwiegender Fehler C1047

Die Objekt- oder Bibliotheksdatei 'datei' wurde mit einem älteren Compiler als andere Objekte erstellt. Erstellen Sie die alten Objekte und Bibliotheken neu.

C1047 wird ausgelöst, wenn Objektdateien oder Bibliotheken, die mit **/LTCG** erstellt wurden, miteinander verknüpft werden, die Objektdateien oder Bibliotheken aber mit verschiedenen Versionen des Visual C++-Toolsets erstellt wurden.

Dies kann auftreten, wenn Sie beginnen, eine neue Compilerversion zu verwenden, für vorhandene Objektdateien oder Bibliotheken aber keine Neuerstellung von Grund auf ausführen.

Um Fehler C1047 zu beheben, erstellen Sie alle Objektdateien und Bibliotheken neu.