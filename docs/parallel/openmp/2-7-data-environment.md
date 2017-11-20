---
title: 2.7 Datenumgebung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4994b018cfbe8395f453cd5964f1d1733f3117e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="27-data-environment"></a>2.7 Datenumgebung
In diesem Abschnitt werden eine Direktive und mehrere Klauseln zum Steuern der datenumgebung während der Ausführung des parallelen Regionen wie folgt:  
  
-   Ein **Threadprivate** Richtlinie (siehe folgenden Abschnitt) dient der um Dateigültigkeitsbereich, Namespace-Gültigkeitsbereich oder Blockbereiche statische Variablen lokalen an einen Thread zu machen.  
  
-   Klauseln, die auf die Richtlinien so steuern Sie die Freigabe Attribute von Variablen für die Dauer der parallelen oder Arbeit-Freigabe-Konstrukte angegeben werden können, werden in beschrieben [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".