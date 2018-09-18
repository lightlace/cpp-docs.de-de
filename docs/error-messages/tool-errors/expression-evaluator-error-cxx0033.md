---
title: Ausdrucksauswertungsfehler CXX0033 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f37b53c30d36a43d339132bfd9baca3e5ec70c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057196"
---
# <a name="expression-evaluator-error-cxx0033"></a>Ausdrucksauswertungsfehler CXX0033

Fehler in OMF-Typinformationen

Die ausführbare Datei kein gültiges Objekt Modulformat (OMF) für das Debuggen.

Dieser Fehler ist mit CAN0033 identisch.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die ausführbare Datei wurde nicht mit dem Linker mit dieser Version von Visual C++ erstellt. Verknüpfen Sie den mit der aktuellen Version von LINK.exe.

1. Die .exe-Datei ist möglicherweise beschädigt. Kompilieren Sie und verknüpfen Sie das Programm.