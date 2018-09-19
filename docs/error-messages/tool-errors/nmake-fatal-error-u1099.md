---
title: 'NMAKE: Schwerwiegender Fehler U1099 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3ef75a1435d8c922087fcdd21d1941961bc82cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113382"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE: Schwerwiegender Fehler U1099

Stapelüberlauf

Das Makefile verarbeitete war zu komplex für den aktuellen Stack-gesamtzuordnung in NMAKE. NMAKE: verfügt über eine Zuweisung von 0 x 3000 (12 KB).

Um Stapelreservierungsgröße von erhöhen möchten, führen die [Editbin Stapelgröße](../../build/reference/stack.md) -Hilfsprogramm mit einem größeren Stack (Option):

**EDITBIN /STACK:reserve NMAKE. EXE-DATEI**

wo *reservieren* ist eine Zahl größer als die aktuelle Stapelreservierungsgröße in NMAKE.