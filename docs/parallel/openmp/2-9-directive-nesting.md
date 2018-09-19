---
title: 2.9 Schachtelung von | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9558180a2f063171be563219f89ec3858e37a5d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396986"
---
# <a name="29-directive-nesting"></a>2.9 Schachtelung von Anweisungen

Dynamische Schachtelung von Anweisungen muss die folgenden Regeln beachtet werden:

- Ein **parallele** dynamisch in einer anderen Richtlinie **parallele** logisch richtet ein neues Team, das nur den aktuellen Thread besteht, es sei denn, die Parallelität geschachtelt ist aktiviert.

- **für**, **Abschnitte**, und **einzelne** Direktiven, die auf die gleiche Bindung **parallele** dürfen nicht ineinander geschachtelt werden.

- **kritische** Anweisungen mit dem gleichen Namen dürfen nicht ineinander geschachtelt werden. Beachten Sie, dass diese Einschränkung ist nicht ausreichend, Deadlocks zu vermeiden.

- **für**, **Abschnitte**, und **einzelne** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **kritische**, **sortiert**, und **master** Regionen aus, wenn die Anweisungen auf die gleiche Bindung **parallele** als Regionen.

- **Barriere** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **für**, **sortiert**, **Abschnitte**, **einzelne**, **master**, und **kritische** Regionen aus, wenn die Anweisungen auf die gleiche Bindung **parallele** als Regionen.

- **Master** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **für**, **Abschnitte**, und **einzelne** Direktiven Wenn die **Master** Anweisungen zu binden, auf die gleiche **parallele** als die gemeinsame Verwendung von Work-Anweisungen.

- **sortiert** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **kritische** Regionen aus, wenn die Anweisungen auf die gleiche Bindung **parallele** als Regionen.

- Jede Richtlinie, die zulässig ist, wenn dynamisch innerhalb eines parallelen Bereichs ausgeführt ist auch zulässig, wenn außerhalb eines parallelen Bereichs ausgeführt. Wenn außerhalb eines parallelen Bereichs von benutzerdefinierten dynamisch ausgeführt wird, wird die Richtlinie von einem Team besteht aus nur die master-Thread ausgeführt.