---
title: 'NMAKE: Schwerwiegender Fehler U1100 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1100
dev_langs:
- C++
helpviewer_keywords:
- U1100
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27ffd33a0a80056ee57f5f088823d7f8f6549c24
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135756"
---
# <a name="nmake-fatal-error-u1100"></a>NMAKE: Schwerwiegender Fehler U1100

das Makro 'Makroname' ist im Kontext der Batchregel "Regel" nicht zulässig

NMAKE: generiert diesen Fehler, wenn der Befehlsblock einer Regel im Batchmodus direkt oder indirekt ein Makro für die besondere Datei verweist, die sich nicht um $<.

$< ist der einzige zulässige Makro für stapelverarbeitungsregeln.