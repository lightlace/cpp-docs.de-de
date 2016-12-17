---
title: "Projektbuildfehler PRJ0019"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0019"
ms.assetid: 5390a62b-aacf-4bc8-b9d7-08f1e0233423
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Tool hat einen Fehlercode aus folgender Quelle zurückgegeben:  
  
 Die Fehlerebene für einen benutzerdefinierten Buildschritt oder ein Buildereignis war ungleich Null.  
  
 Außerdem wird PRJ0019 ausgegeben, wenn von einem Tool zwar ein Fehlercode, aber keine Fehlermeldung zurückgegeben wurde.  Dies kann z. B. vorkommen, wenn Sie die Ausgabe von MIDL an NUL umleiten.  
  
 Weitere Informationen finden Sie unter [Problembehandlung bei benutzerdefinierten Buildschritten und Buildereignissen](../../ide/troubleshooting-build-customizations.md).  
  
 Dieser Fehler kann auch auftreten, wenn Sie Schritte als Mitglied der Gruppe Benutzer ausführen und Administratorzugriff erforderlich ist.  Weitere Informationen finden Sie unter [Ausführen als Mitglied der Gruppe Benutzer](../../top/running-as-a-member-of-the-users-group.md).