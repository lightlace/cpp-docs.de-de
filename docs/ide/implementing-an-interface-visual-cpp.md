---
title: Implementieren einer Schnittstelle (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 896ada2c46c68a794265e7344e9b7f7c7f91aebe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-an-interface-visual-c"></a>Implementieren einer Schnittstelle (Visual C++)
Um eine Schnittstelle zu implementieren, müssen Sie erstellt haben ein Projekt als ATL COM-Anwendung oder als eine MFC-Anwendung, die ATL-Unterstützung enthält. Können Sie die [ATL-Projektassistenten](../atl/reference/atl-project-wizard.md) zum Erstellen einer Anwendung ATL oder [Hinzufügen eines ATL-Objekts zu der MFC-Anwendung](../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.  
  
 Nach des Projekts erstellen, um eine Schnittstelle zu implementieren, müssen Sie zuerst ein ATL-Objekt hinzufügen. Finden Sie unter [Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) eine Liste der Assistenten, mit denen Objekte ATL-Projekt hinzu.  
  
> [!NOTE]
>  Der Assistent unterstützt keine ATL-Dialogfelder, XML-Webdienste mit ATL, Leistungsobjekte oder Leistungsindikatoren.  
  
 Wenn Sie [eine ATL-Steuerelement hinzufügen](../atl/reference/adding-an-atl-control.md), können Sie angeben, ob aufgelisteten Standardschnittstellen implementieren die [Schnittstellen](../atl/reference/interfaces-atl-control-wizard.md) auf der Seite, Assistenten und in atlcom.h definiert.  
  
 Nachdem Sie das Objekt oder ein Steuerelement hinzugefügt haben, können Sie weitere Schnittstellen in jeder Bibliothek verfügbaren Typ implementieren, mit dem Assistenten zum Implementieren einer Schnittstelle.  
  
 Wenn Sie eine neue Schnittstelle hinzufügen, müssen Sie es in das Projekt IDL-Datei manuell hinzufügen. Finden Sie unter [Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt](../atl/reference/adding-a-new-interface-in-an-atl-project.md) für Weitere Informationen.  
  
### <a name="to-implement-an-interface"></a>Eine Schnittstelle implementieren  
  
1.  In der Klassenansicht mit der rechten Maustaste des Klassennamen für das ATL-Objekt.  
  
2.  Klicken Sie auf **hinzufügen** aus dem Kontextmenü, und klicken Sie dann auf **Schnittstelle implementieren** zum Anzeigen der [Assistent zum Implementieren von Schnittstelle](../ide/implement-interface-wizard.md).  
  
3.  Wählen Sie die zu implementierenden Schnittstellen aus den entsprechenden Typbibliotheken und klicken Sie auf **Fertig stellen**.  
  
4.  Erweitern Sie in der Klassenansicht das Objekt Basen und Schnittstellen-Knoten, um die Schnittstelle finden Sie unter Sie implementiert haben, und erweitern Sie dann die Schnittstelle-Knoten, um die verfügbaren Eigenschaften, Methoden und Ereignisse anzuzeigen.  
  
    > [!NOTE]
    >  Sie können auch die [Objektkatalog](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) die Member der Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer COM-Schnittstelle](../ide/creating-a-com-interface-visual-cpp.md)   
 [Bearbeiten einer COM-Schnittstelle](../ide/editing-a-com-interface.md)