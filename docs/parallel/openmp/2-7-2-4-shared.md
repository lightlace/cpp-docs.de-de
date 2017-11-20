---
title: 2.7.2.4 freigegebene | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 974f534003455ccd750ddc1b7c1f3c28b220f1b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="2724-shared"></a>2.7.2.4 shared
Diese Klausel teilt Variablen in der *Variablenliste* auf allen Threads in einem Team. Alle Threads in einem Team Zugriff auf denselben Speicherbereich für **freigegebenen** Variablen.  
  
 Die Syntax der **freigegebenen** -Klausel ist wie folgt:  
  
```  
shared(variable-list)  
```