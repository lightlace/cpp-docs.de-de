---
title: 2.8 Direktivenbindung
ms.date: 11/04/2016
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
ms.openlocfilehash: fb22d1b503303842ff73550c1c6544cae7e5f2f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528617"
---
# <a name="28-directive-binding"></a>2.8 Direktivenbindung

Dynamische Bindung von Direktiven, muss die folgenden Regeln einhalten:

- Die **für**, **Abschnitte**, **einzelne**, **master**, und **Barriere** Direktiven Binden an die dynamisch Einschließen von **parallele**, sofern eine vorhanden, unabhängig vom Wert eines beliebigen ist **Wenn** -Klausel, die auf, dass diese Direktive vorhanden sein kann. Wenn keine parallelen Bereichs derzeit ausgeführt wird, werden die Anweisungen von einem Team besteht aus nur die master-Thread ausgeführt.

- Die **sortiert** Richtlinie gebunden wird, die dynamisch einschließende **für**.

- Die **atomic** Richtlinie gewährt exklusiven Zugriff in Bezug auf **atomic** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.

- Die **kritische** Richtlinie gewährt exklusiven Zugriff in Bezug auf **kritische** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.

- Eine Anweisung kann nie dynamisch für jede Anweisung außerhalb der nächsten binden einschließenden **parallele**.