---
title: 'NMAKE: Schwerwiegender Fehler U1099'
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 395f25d8d27bc5e9b6132c87390c8c3bc19b6cc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298242"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE: Schwerwiegender Fehler U1099

Stapelüberlauf

Das Makefile verarbeitete war zu komplex für den aktuellen Stack-gesamtzuordnung in NMAKE. NMAKE: verfügt über eine Zuweisung von 0 x 3000 (12 KB).

Um Stapelreservierungsgröße von erhöhen möchten, führen die [Editbin Stapelgröße](../../build/reference/stack.md) -Hilfsprogramm mit einem größeren Stack (Option):

**EDITBIN /STACK:reserve NMAKE. EXE-DATEI**

wo *reservieren* ist eine Zahl größer als die aktuelle Stapelreservierungsgröße in NMAKE.