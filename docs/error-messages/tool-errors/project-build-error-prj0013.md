---
title: Projektbuildfehler prj0013 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0013
dev_langs: C++
helpviewer_keywords: PRJ0013
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8694d4bfbc3fe54484a4ec211eb09f7cf2ab1c42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0013"></a>Projektbuildfehler PRJ0013
Möglicherweise sind nicht genügend Systemressourcen vorhanden. Ein Pipe, der zum Starten eines Builds erforderlich ist, konnte nicht erstellt werden.  
  
 Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Systemressourcen vorhanden sind. Sie können diesen Fehler beheben, indem Sie die Systemressourcenauslastung durch andere Prozesse/Anwendungen verringern.  
  
 Dieser Fehler kann auch auftreten, wenn Ihre Sicherheitsstufe nicht zum Erstellen von Pipes ausreicht (siehe [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)).