---
title: "Container: Implementieren eines Containers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [OLE], OLE-Container"
  - "OLE-Container, Implementieren"
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Container: Implementieren eines Containers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel werden die Durchführungsbestimmungen Container zusammen und zeigt auf anderen Artikeln, die weiterführende Erklärungen zum Implementieren von Containern bewerten.  Es werden auch einige optionale OLE\-Funktionen auf, die Sie implementieren sollten und die Elemente, die diese Funktionen beschreiben.  
  
#### Um die von CWinApp abgeleitete Klasse vorbereiten  
  
1.  Initialisieren Sie die OLE\-Bibliotheken, indem Sie in der `InitInstance`**AfxOleInit**\-Memberfunktion aufrufen.  
  
2.  Rufen Sie `CDocTemplate::SetContainerInfo` in `InitInstance` auf, um das Menü zuzuweisen und Zugriffstastenressourcen haben, wann ein eingebettetes Element aktiviert direkt ist.  Weitere Informationen zu diesem Thema, finden Sie unter [Aktivierung](../mfc/activation-cpp.md).  
  
 Diese Funktionen werden automatisch für Sie bereitgestellt, wenn Sie den MFC\-Anwendungs\-Assistenten verwenden, um eine Containeranwendung zu erstellen.  Siehe [Erstellen eines Programms mit MFC](../mfc/reference/mfc-application-wizard.md).  
  
#### So die Ansichtsklasse vorbereiten  
  
1.  Keep track auf ausgewählten Elemente, indem einen Zeiger, oder eine Liste von Zeigern, wenn Sie Mehrfachauswahlen unterstützen, auf den ausgewählten Elementen aus.  Ihre `OnDraw`\-Funktion muss alle OLE\-Elemente zeichnen.  
  
2.  Überschreiben Sie `IsSelected`, um sicherzustellen, dass das Element, das an es übergeben wird, derzeit ausgewählt ist.  
  
3.  Implementieren Sie einen Meldungshandler **OnInsertObject**, um das **Objekt einfügen**  Dialogfeld anzuzeigen.  
  
4.  Implementieren Sie einen Meldungshandler `OnSetFocus`, um den Fokus aus der Ansicht zu einem direkt aktiven OLE eingebetteten Element zu übertragen.  
  
5.  Implementieren Sie einen Meldungshandler `OnSize`, um ein OLE eingebettetes Element erkennen, dass es sein Rechteck ändern muss, damit die Änderung der enthaltenden Ansicht an Größe wiederzugeben.  
  
 Da die Implementierung dieser Funktionen deutlich von einer Anwendung z folgenden ist, stellt der Anwendungs\-Assistent nur eine grundlegende Implementierung.  Sie müssen wahrscheinlich diese Funktionen anpassen, um die Anwendung abzurufen, ordnungsgemäß zu arbeiten.  Ein Beispiel hierfür, finden Sie das Beispiel [CONTAINER](../top/visual-cpp-samples.md).  
  
#### So eingebetteten und verknüpften Elementen des Handles  
  
1.  Leiten Sie eine Klasse von [COleClientItem](../mfc/reference/coleclientitem-class.md).  Objekte dieser Klasse stellen Elemente, die eingecheckt eingebettet wurden oder an OLE\-Dokument verknüpft wurde.  
  
2.  Überschreibung **OnChange**, `OnChangeItemPosition` und `OnGetItemPosition`.  Diese Funktionen behandeln die Größenanpassung und Position, und die eingebetteten und verknüpften Elemente.  
  
 Der Anwendungs\-Assistent berechnet die Klasse für Sie, müssen aber wahrscheinlich **OnChange** und andere Funktionen überschreiben, die mit dem in Schritt 2 der obigen Prozedur aufgelisteten.  Die Implementierungsskelette müssen für die meisten Anwendungen angepasst werden, da diese Funktionen unterscheiden zu einer Anwendung z folgenden implementiert werden.  Beispiele finden Sie dieses den MFC\-Beispielen [DRAWCLI](../top/visual-cpp-samples.md) und [CONTAINER](../top/visual-cpp-samples.md).  
  
 Sie müssen einige Elemente der Menüstruktur der Containeranwendung hinzufügen, um die OLE zu unterstützen.  Weitere Informationen zu dieser, finden Sie unter [Menüs und Ressourcen: Container\-Hinzufügungen](../mfc/menus-and-resources-container-additions.md).  
  
 Sie können auch einige der folgenden Funktionen in der Containeranwendung unterstützen:  
  
-   Direkte Aktivierung, wenn ein eingebettetes Element bearbeitet wird.  
  
     Weitere Informationen finden Sie unter [Aktivierung](../mfc/activation-cpp.md).  
  
-   Erstellung von OLE\-Elementen durch Drag & Drop eine Auswahl von einer Serveranwendung.  
  
     Weitere Informationen finden Sie unter [Drag & Drop \(OLE\)](../mfc/drag-and-drop-ole.md).  
  
-   Links zu eingebetteten Objekten oder den Kombinationscontainer\/server\-Anwendungen.  
  
     Weitere Informationen finden Sie unter [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md).  
  
## Siehe auch  
 [Container](../mfc/containers.md)   
 [Container: Clientelemente](../mfc/containers-client-items.md)