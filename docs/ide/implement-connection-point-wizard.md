---
title: Verbindung Assistent zum Implementieren von | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.impl.cp.overview
dev_langs: C++
helpviewer_keywords: Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f29b4f25d937c2f538373ff85819f7315150e712
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implement-connection-point-wizard"></a>Assistent zum Implementieren von Verbindungspunkten
Dieser Assistent implementiert einen Verbindungspunkt für ein COM-Objekt. Ein verbindungsfähiges Objekt (d. h. eine Quelle) kann einen Verbindungspunkt für seine eigenen Schnittstellen oder für jede Ausgangsschnittstelle verfügbar machen. Geben Sie sowohl Visual C++ als auch Windows Typbibliotheken, die Ausgangsschnittstellen haben. Jede Ausgangsschnittstelle kann von einem Client auf ein Objekt (d. h. eine Senke) implementiert werden.  
  
 Weitere Informationen finden Sie unter [ATL-Verbindungspunkte](../atl/atl-connection-points.md).  
  
 **Verfügbare Typbibliotheken**  
 Zeigt die verfügbaren Typbibliotheken, enthält die Schnittstellendefinitionen, die für die Verbindungspunkte implementiert werden können. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um eine Datei mit der Typbibliothek verwenden suchen.  
  
 **Speicherort**  
 Zeigt den Speicherort der Typbibliothek, die derzeit im ausgewählten der **verfügbaren Typbibliotheken** Liste.  
  
 **Schnittstellen**  
 Zeigt die Schnittstellen, deren Definitionen werden in der Typbibliothek, die derzeit im ausgewählten enthalten, die **verfügbaren Typbibliotheken** Feld.  
  
|Übertragen Sie die Schaltfläche|Beschreibung|  
|---------------------|-----------------|  
|**>**|Hinzugefügt, die **Implementieren von Verbindungspunkten** Liste der derzeit im ausgewählten Schnittstellenname der **Schnittstellen** Liste.|  
|**>>**|Hinzugefügt, die **Implementieren von Verbindungspunkten** Liste alle Schnittstellennamen in verfügbaren der **Schnittstellen** Liste.|  
|**<**|Entfernt die derzeit im ausgewählten Schnittstelle die **Implementieren von Verbindungspunkten** Liste.|  
|**<<**|Entfernt alle derzeit aufgeführt Schnittstellennamen, der **Implementieren von Verbindungspunkten** Liste.|  
  
 **Implementieren von Verbindungspunkten**  
 Zeigt die Namen der Schnittstellen, die für die Sie Verbindungspunkte implementieren, wenn Sie auf **Fertig stellen**.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren eines Verbindungspunktes](../ide/implementing-a-connection-point-visual-cpp.md)