---
title: Projektbuildfehler PRJ0019 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0019
dev_langs:
- C++
helpviewer_keywords:
- PRJ0019
ms.assetid: 5390a62b-aacf-4bc8-b9d7-08f1e0233423
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 509c346d0452969d891ab03d67737beb6797bf28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0019"></a>Projektbuildfehler PRJ0019
Ein Tool hat einen Fehlercode aus zurückgegeben.  
  
 Eine Fehlerstufe erreicht war ungleich NULL für einen benutzerdefinierten Buildschritt oder ein Buildereignis.  
  
 Sie werden PRJ0019, wenn ein Tool ein Fehlercode aber keine Fehlermeldung zurückgegeben. Dies kann beispielsweise vorkommen, wenn Sie die Ausgabe von MIDL an NUL umleiten.  
  
 Finden Sie unter [Problembehandlung benutzerdefinierte Buildschritte und Buildereignisse](../../ide/troubleshooting-build-customizations.md) für Weitere Informationen.  
  
 Dieser Fehler kann auch auftreten, wenn Sie als Mitglied der Gruppe der Benutzer ausführen und Administratorzugriff erforderlich ist. Weitere Informationen finden Sie unter [Ausführen als Mitglied der Gruppe "Benutzer"](../../security/running-as-a-member-of-the-users-group.md).