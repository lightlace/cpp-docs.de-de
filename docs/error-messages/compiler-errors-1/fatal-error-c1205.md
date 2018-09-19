---
title: Schwerwiegender Fehler C1205 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1205
dev_langs:
- C++
helpviewer_keywords:
- C1205
ms.assetid: f855c145-8cf7-4dd1-bb19-257ee38b8382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e70be77c224b8c1c6039a908d38e8e482ab36259
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035564"
---
# <a name="fatal-error-c1205"></a>Schwerwiegender Fehler C1205

Generika werden von der installierten Laufzeitversion nicht unterstützt.

Die vom Compiler verwendete Version der Common Language Runtime ist keine Version der Laufzeit, die vom aktuellen Compiler unterstützt wird.  Beispielsweise erfordert die Generika-Funktion eine Laufzeit, die auf den Compiler zugeschnitten ist.

Die Pfadangabe muss möglicherweise geändert werden.