---
title: "Assistent zum Implementieren von Verbindungspunkten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.impl.cp.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Implementieren von Verbindungspunkten [C++]"
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Assistent zum Implementieren von Verbindungspunkten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten implementieren Sie einen Verbindungspunkt für ein COM\-Objekt.  Ein verbindungsfähiges Objekt \(d. h. eine Quelle\) kann für seine eigenen Schnittstellen oder für beliebige Ausgangsschnittstellen einen Verbindungspunkt zur Verfügung stellen.  Sowohl Visual C\+\+ als auch Windows bieten Typbibliotheken mit Ausgangsschnittstellen.  Jede Ausgangsschnittstelle kann von einem Client für ein Objekt \(d. h. eine Senke\) implementiert werden.  
  
 Weitere Informationen finden Sie unter [ATL\-Verbindungspunkte](../atl/atl-connection-points.md).  
  
 **Verfügbare Typbibliotheken**  
 Zeigt die verfügbaren Typbibliotheken mit Schnittstellendefinitionen an, für die Sie Verbindungspunkte implementieren können.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um eine Datei zu suchen, die die gewünschte Typbibliothek enthält.  
  
 **Speicherort**  
 Zeigt den Speicherort der Typbibliothek an, die derzeit in der Liste **Verfügbare Typbibliotheken** markiert ist.  
  
 **Schnittstellen**  
 Zeigt die Schnittstellen an, deren Definitionen in der Typbibliothek enthalten sind, die derzeit im Feld **Verfügbare Typbibliotheken** markiert ist.  
  
|Übertragungsschaltfläche|Beschreibung|  
|------------------------------|------------------|  
|**\>**|Fügt der Liste **Verbindungspunkte implementieren** den Schnittstellennamen hinzu, der derzeit in der Liste **Schnittstellen** markiert ist.|  
|**\>\>**|Fügt der Liste **Verbindungspunkte implementieren** alle Schnittstellennamen hinzu, die derzeit in der Liste **Schnittstellen** verfügbar sind.|  
|**\<**|Entfernt den derzeit markierten Schnittstellennamen aus der Liste **Verbindungspunkte implementieren**.|  
|**\<\<**|Entfernt alle derzeit in der Liste **Verbindungspunkte implementieren** enthaltenen Schnittstellennamen.|  
  
 **Verbindungspunkte implementieren**  
 Zeigt die Namen der Schnittstellen an, für die Verbindungspunkte implementiert werden, nachdem Sie auf **Fertig stellen** geklickt haben.  
  
## Siehe auch  
 [Implementieren eines Verbindungspunktes](../ide/implementing-a-connection-point-visual-cpp.md)