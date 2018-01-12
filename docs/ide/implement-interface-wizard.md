---
title: Implementieren der Schnittstelle-Assistenten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.impl.interface.overview
dev_langs: C++
helpviewer_keywords: Implement Interface Wizard [C++]
ms.assetid: 947c329e-0815-4ca7-835e-c41dfeb75f9e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d224546eb8bb06421c2e84206e1f4d4dc77f9668
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implement-interface-wizard"></a>Assistent zum Implementieren von Schnittstellen
Dieser Assistent implementiert eine Schnittstelle für ein COM-Objekt. Implementierungen von vielen Schnittstellen sind in der COM-Bibliotheken in Visual Studio und Windows verfügbare enthalten. Eine Implementierung bezieht sich auf ein Objekt zur Verfügung, wenn eine Instanz dieses Objekts erstellt wird, und darüber, dass die Dienste, die das Objekt bietet.  
  
 Eine Erläuterung der Schnittstellen und Implementierungen, finden Sie unter [Schnittstellen und Schnittstellenimplementierungen](http://msdn.microsoft.com/library/windows/desktop/ms694356) im Windows SDK.  
  
 **Schnittstelle implementieren aus**  
 Gibt den Speicherort der Typbibliothek, aus der die Schnittstelle erstellt wird.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Projekt**|Die Typbibliothek ist Teil des Projekts.|  
|**Registry**|Die Typbibliothek ist im System registriert. Registrierte Typbibliotheken in aufgelisteten **verfügbaren Typbibliotheken**.|  
|**Datei**|Die Typbibliothek ist nicht unbedingt im System registriert, aber in einer Datei enthalten ist. Geben Sie den Dateispeicherort in **Speicherort**.|  
  
 **Verfügbare Typbibliotheken**  
 Zeigt die verfügbaren Typbibliotheken mit Schnittstellendefinitionen, die Sie implementieren können. Wenn Sie auf **Datei** unter **Schnittstelle implementieren aus**, dieses Feld ist für die Änderung nicht verfügbar.  
  
 **Speicherort**  
 Zeigt den Speicherort der Typbibliothek, die derzeit im ausgewählten der **verfügbaren Typbibliotheken** Liste. Wenn Sie ausgewählt haben **Datei** unter **Schnittstelle implementieren aus**, klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um eine Datei mit der Typbibliothek verwenden suchen.  
  
 **Schnittstellen**  
 Zeigt die Schnittstellen, deren Definitionen werden in der Typbibliothek, die derzeit im ausgewählten enthalten, die **verfügbaren Typbibliotheken** Feld.  
  
> [!NOTE]
>  Schnittstellen, die den gleichen Namen haben wie die vom ausgewählten Objekt bereits implementiert nicht, in angezeigt werden der **Schnittstellen** Feld.  
  
|Übertragen Sie die Schaltfläche|Beschreibung|  
|---------------------|-----------------|  
|**>**|Hinzugefügt, die **Schnittstellen implementieren** Liste der derzeit im ausgewählten Schnittstellenname der **Schnittstellen** Liste.|  
|**>>**|Hinzugefügt, die **Schnittstellen implementieren** Liste alle Schnittstellennamen in verfügbaren der **Schnittstellen** Liste.|  
|**<**|Entfernt die derzeit im ausgewählten Schnittstelle die **Schnittstellen implementieren** Liste.|  
|**<\<**|Entfernt alle derzeit aufgeführt Schnittstellennamen, der **Schnittstellen implementieren** Liste.|  
  
 **Implementieren von Schnittstellen**  
 Zeigt die Namen der Schnittstellen, die Sie ausgewählt haben, um für das Objekt zu implementieren.  
  
> [!NOTE]
>  Wenn Sie mehr als eine Schnittstelle enthalten, die abgeleitet `IDispatch`, oder Sie müssen die Einträge COM_MAP eindeutig machen, wenn Sie versuchen, eine Schnittstelle zu implementieren, die von einer anderen Schnittstelle, die bereits in der Klasse abgeleitet ist. Finden Sie unter [COM_INTERFACE_ENTRY2](../atl/reference/com-interface-entry-macros.md#com_interface_entry2) für Weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md)