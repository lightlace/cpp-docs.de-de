---
title: 2.8 Direktivenbindung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a70dbc0306005473d427015e81d8b93e895da9fa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="28-directive-binding"></a>2.8 Direktivenbindung
Dynamisches Binden von Direktiven muss die folgenden Regeln einhalten:  
  
-   Die **für**, **Abschnitte**, **einzelne**, **master**, und **Barriere** Direktiven Binden an die dynamisch Einschließen von **parallele**, sofern, unabhängig vom Wert eines beliebigen vorhanden **Wenn** -Klausel, die auf diese Richtlinie vorhanden sein kann. Wenn keine parallelen Bereichs derzeit ausgeführt wird, werden die Richtlinien von einem Team besteht nur die master-Thread ausgeführt.  
  
-   Die **sortiert** -Direktive bindet an die dynamisch einschließende **für**.  
  
-   Die **atomic** Richtlinie erzwingt exklusiven Zugriff in Bezug auf **atomic** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.  
  
-   Die **kritische** Richtlinie erzwingt exklusiven Zugriff in Bezug auf **kritische** Direktiven in allen Threads, nicht nur das aktuelle Teamprojekt.  
  
-   Eine Richtlinie kann nie dynamisch an keiner anderen Direktive außerhalb der nächsten binden einschließenden **parallele**.