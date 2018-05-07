---
title: Projektbuildfehler prj0013 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0013
dev_langs:
- C++
helpviewer_keywords:
- PRJ0013
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d055043d5c7e7b030557ab03ceb7181c664ce01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="project-build-error-prj0013"></a>Projektbuildfehler PRJ0013
Möglicherweise sind nicht genügend Systemressourcen vorhanden. Ein Pipe, der zum Starten eines Builds erforderlich ist, konnte nicht erstellt werden.  
  
 Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Systemressourcen vorhanden sind. Sie können diesen Fehler beheben, indem Sie die Systemressourcenauslastung durch andere Prozesse/Anwendungen verringern.  
  
 Dieser Fehler kann auch auftreten, wenn Ihre Sicherheitsstufe nicht zum Erstellen von Pipes ausreicht (siehe [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)).