---
title: 2.7 Datenumgebung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1b0f253ce14ffc5d3740e582a9a51feea56ad32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690064"
---
# <a name="27-data-environment"></a>2.7 Datenumgebung
In diesem Abschnitt werden eine Direktive und mehrere Klauseln zum Steuern der datenumgebung während der Ausführung des parallelen Regionen wie folgt:  
  
-   Ein **Threadprivate** Richtlinie (siehe folgenden Abschnitt) dient der um Dateigültigkeitsbereich, Namespace-Gültigkeitsbereich oder Blockbereiche statische Variablen lokalen an einen Thread zu machen.  
  
-   Klauseln, die auf die Richtlinien so steuern Sie die Freigabe Attribute von Variablen für die Dauer der parallelen oder Arbeit-Freigabe-Konstrukte angegeben werden können, werden in beschrieben [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".