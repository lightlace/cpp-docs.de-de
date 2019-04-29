---
title: Ausdrucksauswertungsfehler CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 8563eb2fbc24c6ad8db639d2e227802412a16090
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397054"
---
# <a name="expression-evaluator-error-cxx0033"></a>Ausdrucksauswertungsfehler CXX0033

Fehler in OMF-Typinformationen

Die ausführbare Datei kein gültiges Objekt Modulformat (OMF) für das Debuggen.

Dieser Fehler ist mit CAN0033 identisch.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Die ausführbare Datei wurde nicht mit dem Linker mit dieser Version von Visual C++ erstellt. Verknüpfen Sie den mit der aktuellen Version von LINK.exe.

1. Die .exe-Datei ist möglicherweise beschädigt. Kompilieren Sie und verknüpfen Sie das Programm.