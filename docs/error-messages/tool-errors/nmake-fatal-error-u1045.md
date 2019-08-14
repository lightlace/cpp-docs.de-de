---
title: 'NMAKE: Schwerwiegender Fehler U1045'
ms.date: 08/11/2019
f1_keywords:
- U1045
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
ms.openlocfilehash: bdc28bcf02aea791a346a0a74915707fef551b8b
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980545"
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE: Schwerwiegender Fehler U1045

> Fehler beim erzeugen: *Meldung*

Ein von NMAKE aufgerufener Programm oder Befehl konnte aus Grund in der *Nachricht*nicht ausgeführt werden. Wenn NMAKE ein anderes Programm aufruft, z. b. den Compiler oder den Linker, kann der Aufruf fehlschlagen. Oder vom aufgerufenen Programm kann ein Fehler zurückgegeben werden. Diese Meldung wird verwendet, um den Fehler zu melden.

Um dieses Problem zu beheben, müssen Sie zunächst die Ursache des Fehlers bestimmen. Sie können die von der NMAKE [/N](../../build/reference/running-nmake.md#nmake-options) -Option gemeldeten Befehle verwenden, um die Umgebungseinstellungen zu überprüfen und die Aktionen zu wiederholen, die von NMAKE in der Befehlszeile ausgeführt werden.
