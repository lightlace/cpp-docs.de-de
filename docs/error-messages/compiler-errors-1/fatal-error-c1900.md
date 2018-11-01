---
title: Schwerwiegender Fehler C1900
ms.date: 11/04/2016
f1_keywords:
- C1900
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
ms.openlocfilehash: c4622dd4552f7bfcc822a3aab4d5783146d68ac7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581856"
---
# <a name="fatal-error-c1900"></a>Schwerwiegender Fehler C1900

> Konflikt zwischen "*tool1*'Version'*" number1 "*'und'*tool2*'Version'*" number2 "*"

In verschiedenen Durchläufen des Compilers ausgeführte Tools stimmen nicht überein. *"number1"* und *"number2"* finden Sie die Datumsangaben der Dateien. Z. B. führt in Durchgang 1 durch das Compiler-front End (c1.dll) ausgeführt und in Durchgang 2 führt der Compiler-back-End (c2.dll) aus. Die Datumsangaben der Dateien müssen übereinstimmen.

Um dieses Problem zu beheben, stellen Sie sicher, dass alle Aktualisierungen auf Visual Studio angewendet wurden. Wenn das Problem weiterhin besteht, verwenden Sie **Programme und Funktionen** in der Windows-Systemsteuerung zu reparieren oder installieren Sie Visual Studio.