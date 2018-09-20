---
title: 2.4 Arbeitsteilungskonstrukte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 719b33698b708761f0cd56e65a70a6ea8fa3b053
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411117"
---
# <a name="24-work-sharing-constructs"></a>2.4 Arbeitsteilungskonstrukte

Ein Konstrukt Freigabe von Arbeit verteilt, die Ausführung der Anweisung zugeordnet, unter den Mitgliedern des Teams, die auftreten. Die gemeinsame Verwendung von Work-Anweisungen neue Threads nicht starten, und besteht keine implizite Hindernisse beim Einstieg in eine gemeinsame Verwendung von Work-Konstrukt.

Erstellt die Abfolge der Freigabe von Arbeit und **Barriere** Direktiven, die auftreten müssen für jeden Thread in einem Team identisch sein.

OpenMP definiert die folgenden Arbeitsteilungskonstrukte, und diese werden in den folgenden Abschnitten beschrieben:

- **für** Richtlinie

- **Abschnitte** Richtlinie

- **einzelne** Richtlinie