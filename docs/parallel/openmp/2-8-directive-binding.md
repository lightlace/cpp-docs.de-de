---
title: 2.8 Direktivenbindung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc5b702b17e01bb8d4625a837abdb71086113e68
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415901"
---
# <a name="28-directive-binding"></a>2.8 Direktivenbindung

Dynamische Bindung von Direktiven, muss die folgenden Regeln einhalten:

- Die **für**, **Abschnitte**, **einzelne**, **master**, und **Barriere** Direktiven Binden an die dynamisch Einschließen von **parallele**, sofern eine vorhanden, unabhängig vom Wert eines beliebigen ist **Wenn** -Klausel, die auf, dass diese Direktive vorhanden sein kann. Wenn keine parallelen Bereichs derzeit ausgeführt wird, werden die Anweisungen von einem Team besteht aus nur die master-Thread ausgeführt.

- Die **sortiert** Richtlinie gebunden wird, die dynamisch einschließende **für**.

- Die **atomic** Richtlinie gewährt exklusiven Zugriff in Bezug auf **atomic** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.

- Die **kritische** Richtlinie gewährt exklusiven Zugriff in Bezug auf **kritische** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.

- Eine Anweisung kann nie dynamisch für jede Anweisung außerhalb der nächsten binden einschließenden **parallele**.