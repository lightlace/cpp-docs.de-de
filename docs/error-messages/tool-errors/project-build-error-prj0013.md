---
title: Projektbuildfehler prj0013 | Microsoft-Dokumentation
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
ms.openlocfilehash: aeb0ac9011697c440667a538bd1805780810fb4a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221558"
---
# <a name="project-build-error-prj0013"></a>Projektbuildfehler PRJ0013
Möglicherweise sind nicht genügend Systemressourcen vorhanden. Ein Pipe, der zum Starten eines Builds erforderlich ist, konnte nicht erstellt werden.  
  
 Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Systemressourcen vorhanden sind. Sie können diesen Fehler beheben, indem Sie die Systemressourcenauslastung durch andere Prozesse/Anwendungen verringern.  
  
 Dieser Fehler kann auch auftreten, wenn Ihre Sicherheitsstufe nicht zum Erstellen von Pipes ausreicht (siehe [CreatePipe](https://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)).