---
title: Schwerwiegender Fehler C1026
ms.date: 11/04/2016
f1_keywords:
- C1026
helpviewer_keywords:
- C1026
ms.assetid: 89bb9d40-673a-44aa-a9f4-b42c07b49d44
ms.openlocfilehash: b1a659967a9a62cb79e1084f7d1fa1729bae14da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347128"
---
# <a name="fatal-error-c1026"></a>Schwerwiegender Fehler C1026

Stapelüberlauf im Parser, Programm zu komplex

Der Speicherplatz erforderlich, um das Programm analysiert verursacht einen Stapelüberlauf des Compilers.

Verringern Sie die Komplexität der Ausdrücke, nach:

- Verringern die Schachtelung im `for` und `switch` Anweisungen. Fügen Sie weitere tief geschachtelte Anweisungen in separate Funktionen an.

- Teilen Sie lange Ausdrücke, die durch Trennzeichen Operatoren oder Funktionsaufrufe einschließen.