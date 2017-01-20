---
title: "Container: Client-Element-Benachrichtigungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Clientelemente und OLE-Container"
  - "Benachrichtigungen, Container-Clientelemente"
  - "OLE-Container, Clientelement-Benachrichtigungen"
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Container: Client-Element-Benachrichtigungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden die überschreibbaren Funktionen, die das MFC\-Framework aufruft, wenn Serveranwendungen Elemente im Dokument der Clientanwendung ändern.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) definiert einige überschreibbare Funktionen, die bei Anforderungen aus der Teil\-Anwendung aufgerufen werden, die auch die Serveranwendung aufgerufen wird.  Diese schreibbaren Elemente werden normalerweise als Benachrichtigungen auf.  Sie informieren die Containeranwendung über verschiedene Ereignisse, z Bildlauf, Aktivierung oder eine Meinungsänderung, und von den Änderungen, die erfolgt der diesen beruhen, Benutzer, wenn er bearbeitet oder andernfalls das Element bearbeitet.  
  
 Das Framework setzt Ihre Containeranwendung von Änderungen durch einen Aufruf an `COleClientItem::OnChange`, eine überschreibbare Funktion, deren Implementierung erforderlich ist.  Diese geschützte Funktion erhält zwei Argumente.  Das erste gibt den Grund an, den der Server das Element ändert:  
  
|Benachrichtigung|Bedeutung|  
|----------------------|---------------|  
|`OLE_CHANGED`|Die Darstellung des OLE\-Elements wurde geändert.|  
|`OLE_SAVED`|Das OLE\-Element wurde gespeichert.|  
|`OLE_CLOSED`|Das OLE\-Element ist geschlossen.|  
|**OLE\_RENAMED**|Das Serverdokument, welches das OLE\-Element enthält, wurde umbenannt.|  
|`OLE_CHANGED_STATE`|Das OLE\-Element wurde von den Zuständen geändert.|  
|**OLE\_CHANGED\_ASPECT**|Der Aspekt Videofunktionen des OLE\-Elements ist vom Framework geändert.|  
  
 Diese Werte sind von der **OLE\_NOTIFICATION**\-Enumeration, die in AFXOLE.H. definiert wird.  
  
 Das zweite Argument für dieser Funktion gibt an, wie das Element geändert wurde, oder in welchen Zustand sie eingegeben hat:  
  
|Wenn erstes Argument ist|Zweites Argument|  
|------------------------------|----------------------|  
|`OLE_SAVED` oder `OLE_CLOSED`|Wird nicht verwendet.|  
|`OLE_CHANGED`|Gibt den Aspekt des OLE\-Elements an, die geändert hat.|  
|`OLE_CHANGED_STATE`|Beschreibt den Zustand, der eingegeben wird \(`emptyState`, **loadedState**, `openState`, `activeState` oder `activeUIState`\).|  
  
 Weitere Informationen zu den Bedingungen, die ein Clientelement annehmen kann, finden Sie unter [Container: Client\-Element\-Zustände](../mfc/containers-client-item-states.md).  
  
 Das Framework ruft `COleClientItem::OnGetItemPosition` auf, wenn ein Element für die direkte Bearbeitung aktiviert ist.  Implementierung ist für Anwendungen erforderlich, die direkte Bearbeitung unterstützen.  Der MFC\-Anwendungs\-Assistent stellt eine grundlegende Implementierung bereit, die die Koordinaten des Elements zum `CRect`\-Objekt zugewiesen wird, das als Argument an `OnGetItemPosition` übergeben wird.  
  
 Wenn die Position oder die Größe eines OLE\-Elements während der direkten Bearbeitung ändert, müssen die Informationen des Containers über die Position des Elements und die Ausschneiderechtecke aktualisiert und der Server muss Informationen über die Änderungen abrufen.  Das Framework ruft `COleClientItem::OnChangeItemPosition` zu diesem Zweck auf.  Der MFC\-Anwendungs\-Assistent bietet eine Überschreibung bereit, die die Funktion der Basisklasse aufruft.  Sie sollten die Funktion bearbeiten, die der Anwendungs\-Assistent für das `COleClientItem` abgeleitete Klasse schreiben, damit die Funktion alle Informationen aktualisiert, die vom ClientElementobjekt beibehalten werden.  
  
## Siehe auch  
 [Container](../mfc/containers.md)   
 [Container: Client\-Element\-Zustände](../mfc/containers-client-item-states.md)   
 [COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)