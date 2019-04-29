---
title: 'NMAKE: Schwerwiegender Fehler U1100'
ms.date: 11/04/2016
f1_keywords:
- U1100
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
ms.openlocfilehash: a1474acab4ca4929fb4db4b7b78d7a96637a0745
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298281"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE: Schwerwiegender Fehler U1100

das Makro 'Makroname' ist im Kontext der Batchregel "Regel" nicht zulässig

NMAKE: generiert diesen Fehler, wenn der Befehlsblock einer Regel im Batchmodus direkt oder indirekt ein Makro für die besondere Datei verweist, die sich nicht um $<.

$< ist der einzige zulässige Makro für stapelverarbeitungsregeln.