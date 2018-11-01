---
title: 2.4 Arbeitsteilungskonstrukte
ms.date: 11/04/2016
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
ms.openlocfilehash: e7bf8d37ecdc6a3ef451c9d9746fb47a76a16eb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502881"
---
# <a name="24-work-sharing-constructs"></a>2.4 Arbeitsteilungskonstrukte

Ein Konstrukt Freigabe von Arbeit verteilt, die Ausführung der Anweisung zugeordnet, unter den Mitgliedern des Teams, die auftreten. Die gemeinsame Verwendung von Work-Anweisungen neue Threads nicht starten, und besteht keine implizite Hindernisse beim Einstieg in eine gemeinsame Verwendung von Work-Konstrukt.

Erstellt die Abfolge der Freigabe von Arbeit und **Barriere** Direktiven, die auftreten müssen für jeden Thread in einem Team identisch sein.

OpenMP definiert die folgenden Arbeitsteilungskonstrukte, und diese werden in den folgenden Abschnitten beschrieben:

- **für** Richtlinie

- **Abschnitte** Richtlinie

- **einzelne** Richtlinie