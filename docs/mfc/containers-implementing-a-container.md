---
title: 'Container: Implementieren eines Containers | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- applications [OLE], OLE container
- OLE containers [MFC], implementing
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e43e1fb1c52413eaae05dcbe8331b1d48dd7e2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="containers-implementing-a-container"></a>Container: Implementieren eines Containers
In diesem Artikel werden die Verfahren zum Implementieren eines Containers zusammengefasst und verweist auf die anderen Artikeln, die ausführlichere erläuterungen zum Implementieren von Containern enthalten. Außerdem werden einige optionale OLE-Funktionen, die Sie implementieren möchten, und die Artikel beschreiben diese Funktionen aufgeführt.  
  
#### <a name="to-prepare-your-cwinapp-derived-class"></a>So bereiten Sie Ihre CWinApp abgeleitete Klasse vor  
  
1.  Initialisieren die OLE-Bibliotheken durch Aufrufen von **AfxOleInit** in die `InitInstance` Memberfunktion.  
  
2.  Rufen Sie `CDocTemplate::SetContainerInfo` in `InitInstance` zur Zuweisung des Menü und der Zugriffstaste Ressourcen verwendet, wenn ein eingebettetes Element direktes aktiviert. Weitere Informationen zu diesem Thema finden Sie unter [Aktivierung](../mfc/activation-cpp.md).  
  
 Diese Funktionen werden automatisch bereitgestellt, wenn Sie den Assistenten zum MFC-Anwendungen verwenden, um eine Steuerelementcontainer-Anwendung erstellen. Finden Sie unter [erstellen ein MFC-EXE-Programm](../mfc/reference/mfc-application-wizard.md).  
  
#### <a name="to-prepare-your-view-class"></a>So bereiten Sie Ihre Ansichtsklasse vor  
  
1.  Behalten Sie den Überblick über ausgewählter Elemente mithilfe eines Zeigers oder eine Liste von Zeigern auf, wenn Sie die Mehrfachauswahl, um die ausgewählten Elemente unterstützen. Ihre `OnDraw` Funktion muss alle OLE-Elemente zu zeichnen.  
  
2.  Überschreiben Sie `IsSelected` zu überprüfen, ob das übergebene Element derzeit ausgewählt ist.  
  
3.  Implementieren einer **OnInsertObject** Message-Handler zum Anzeigen der **Objekt einfügen** (Dialogfeld).  
  
4.  Implementieren einer `OnSetFocus` Message-Handler, an den Fokus aus der Ansicht um eine direkte aktive OLE übertragen eingebettet Element.  
  
5.  Implementieren einer `OnSize` Nachrichtenhandler informiert Sie eine OLE eingebettet Element an, dass sie das Rechteck entsprechend der Änderung der Größe der enthaltenen Ansicht geändert werden muss.  
  
 Da die Implementierung dieser Funktionen erheblich von einer Anwendung zur nächsten ändert, stellt der Anwendungs-Assistent nur eine grundlegende Implementierung bereit. Sie müssen wahrscheinlich Anpassen dieser Funktionen, um die Anwendung ordnungsgemäß funktioniert. Ein Beispiel hierfür finden Sie unter der [CONTAINER](../visual-cpp-samples.md) Beispiel.  
  
#### <a name="to-handle-embedded-and-linked-items"></a>Eingebettete und verknüpfte Elemente behandelt.  
  
1.  Leiten Sie eine Klasse von [COleClientItem](../mfc/reference/coleclientitem-class.md). Objekte dieser Klasse dargestellt, Elemente, die in eingebettet oder in Ihr Dokument OLE verknüpft wurden.  
  
2.  Überschreiben Sie **OnChange**, `OnChangeItemPosition`, und `OnGetItemPosition`. Diese Funktionen behandeln, Größe und Positionierung eingebettete und verknüpfte Elemente ändern.  
  
 Der Anwendungs-Assistent wird zum Ableiten der Klasse für Sie, aber Sie müssen wahrscheinlich überschreiben **OnChange** und die andere Funktionen, die mit ihm in Schritt 2 in der vorherigen Prozedur aufgeführt. Das Gerüst eines Implementierungen müssen für die meisten Anwendungen angepasst werden, da diese Funktionen aus einer Anwendung in der nächsten auf andere Weise implementiert werden. Beispiele hierzu finden Sie unter MFC-Beispiele [DRAWCLI](../visual-cpp-samples.md) und [CONTAINER](../visual-cpp-samples.md).  
  
 Sie müssen die containeranwendung Menüstruktur zur Unterstützung von OLE eine Anzahl von Elementen hinzufügen. Weitere Informationen dazu finden Sie unter [Menüs und Ressourcen: Containererweiterungen](../mfc/menus-and-resources-container-additions.md).  
  
 Sie können auch einige der folgenden Funktionen in der containeranwendung unterstützen:  
  
-   Direkte Aktivierung, wenn Sie ein eingebettetes Element zu bearbeiten.  
  
     Weitere Informationen finden Sie unter [Aktivierung](../mfc/activation-cpp.md).  
  
-   Erstellung von OLE Elemente per Drag & Drop eine Auswahl aus einer Server-Anwendung.  
  
     Weitere Informationen finden Sie unter [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md).  
  
-   Enthält Links zu eingebetteten Objekten oder Kombination Container/Server-Anwendungen.  
  
     Weitere Informationen finden Sie unter [Container: Erweiterte Funktionen](../mfc/containers-advanced-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Containers](../mfc/containers.md)   
 [Container: Clientelemente](../mfc/containers-client-items.md)

