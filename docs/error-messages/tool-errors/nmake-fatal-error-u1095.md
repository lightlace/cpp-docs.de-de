---
title: 'NMAKE: Schwerwiegender Fehler U1095 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1095
dev_langs:
- C++
helpviewer_keywords:
- U1095
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 964ec1d029e56a5d9d78659ad919c71a4e44506d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039880"
---
# <a name="nmake-fatal-error-u1095"></a>NMAKE: Schwerwiegender Fehler U1095

Erweiterte Befehlszeile "Commandline" zu lang.

Nach der makroerweiterung hat die angegebene Befehlszeile die maximale Länge von Befehlszeilen für das Betriebssystem überschritten.

MS-DOS lässt bis zu 128 Zeichen in einer Befehlszeile an.

Wenn der Befehl für ein Programm, die Befehlszeileneingabe aus einer Datei akzeptieren kann ist, ändern Sie den Befehl aus, und Bereitstellen Sie Eingaben aus einer Datei auf Datenträger oder eine Inlinedatei. LINK und LIB akzeptiert z. B. die Eingabe aus einer Antwortdatei.