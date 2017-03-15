---
title: "Assistent zum Implementieren von Schnittstellen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.impl.interface.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistent zum Implementieren von Schnittstellen [C++]"
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Assistent zum Implementieren von Schnittstellen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Assistent implementiert eine Schnittstelle für ein COM\-Objekt.  Die COM\-Bibliotheken in Visual Studio und Windows enthalten bereits Implementierungen zahlreicher Schnittstellen.  Eine Schnittstellenimplementierung wird mit einem Objekt verknüpft, sobald eine Instanz dieses Objekts erstellt wird. Sie enthält die Dienste, die vom Objekt zur Verfügung gestellt werden.  
  
 Eine Erläuterung zu Schnittstellen und Implementierungen finden Sie unter [Interfaces and Interface Implementations](http://msdn.microsoft.com/library/windows/desktop/ms694356) im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 **Schnittstelle implementieren aus**  
 Gibt den Speicherort der Typbibliothek an, von der die Schnittstelle aus erstellt wird.  
  
|Option|Beschreibung|  
|------------|------------------|  
|**Project**|Die Typbibliothek ist Teil des Projekts.|  
|**Registrierung**|Die Typbibliothek ist im System registriert.  Registrierte Typbibliotheken sind unter **Verfügbare Typbibliotheken** aufgeführt.|  
|**Datei**|Die Typbibliothek muss nicht unbedingt im System registriert sein, sie ist jedoch in einer Datei enthalten.  Das Verzeichnis der Datei muss unter **Speicherort** angegeben werden.|  
  
 **Verfügbare Typbibliotheken**  
 Zeigt die verfügbaren Typbibliotheken mit Schnittstellendefinitionen an, die Sie implementieren können.  Wenn Sie unter **Schnittstelle implementieren aus** auf **Datei** klicken, kann dieses Feld nicht bearbeitet werden.  
  
 **Speicherort**  
 Zeigt den Speicherort der Typbibliothek an, die derzeit in der Liste **Verfügbare Typbibliotheken** markiert ist.  Wenn Sie unter **Schnittstelle implementieren aus** die Option **Datei** ausgewählt haben, klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(...\), um eine Datei zu suchen, die die gewünschte Typbibliothek enthält.  
  
 **Schnittstellen**  
 Zeigt die Schnittstellen an, deren Definitionen in der Typbibliothek enthalten sind, die derzeit im Feld **Verfügbare Typbibliotheken** markiert ist.  
  
> [!NOTE]
>  Schnittstellen, die denselben Namen wie Schnittstellen haben, die vom ausgewählten Objekt bereits implementiert wurden, werden im Feld **Schnittstellen** nicht angezeigt.  
  
|Übertragungsschaltfläche|Beschreibung|  
|------------------------------|------------------|  
|**\>**|Fügt der Liste **Schnittstellen implementieren** den Schnittstellennamen hinzu, der derzeit in der Liste **Schnittstellen** markiert ist.|  
|**\>\>**|Fügt der Liste **Schnittstellen implementieren** alle Schnittstellennamen hinzu, die derzeit in der Liste **Schnittstellen** verfügbar sind.|  
|**\<**|Entfernt den derzeit in der Liste **Schnittstellen implementieren** markierten Schnittstellennamen.|  
|**\<\<**|Entfernt alle derzeit in der Liste **Schnittstellen implementieren** enthaltenen Schnittstellennamen aus der Liste.|  
  
 **Schnittstellen implementieren**  
 Zeigt die Namen der Schnittstellen an, die Sie markiert haben, um sie für das Objekt zu implementieren.  
  
> [!NOTE]
>  Wenn Sie mehr als eine von `IDispatch` abgeleitete Schnittstelle einfügen oder versuchen, eine Schnittstelle zu implementieren, die von einer anderen bereits in der Klasse befindlichen Schnittstelle abgeleitet wird, müssen Sie die COM\_MAP\-Einträge eindeutig kennzeichnen.  Weitere Informationen finden Sie unter [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md).  
  
## Siehe auch  
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)