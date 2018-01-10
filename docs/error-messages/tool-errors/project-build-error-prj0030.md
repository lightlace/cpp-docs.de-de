---
title: Projektbuildfehler prj0030 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0030
dev_langs: C++
helpviewer_keywords: PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6fe537dd8e6705fd5e30929a2480eb1d9ef9119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0030"></a>Projektbuildfehler PRJ0030
Fehler beim Makro-Erweiterung. Werten Sie Rekursion überschritten 32 Ebenen für $(Makro).  
  
 Dieser Fehler wird durch Rekursion in den Makros verursacht. Wenn Sie festlegen, z. B. die **Zwischenverzeichnis** Eigenschaft (finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md)) auf $(intdir), werden Sie Rekursion haben.  
  
 Um diesen Fehler zu beheben, legen Sie keine Makros oder Eigenschaften in Bezug auf die Makros, die sie verwendet werden, um zu definieren.