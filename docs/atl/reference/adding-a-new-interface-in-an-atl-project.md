---
title: "Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8e4916c60310dd8dcbf0bb9e8c1f151309a32621
ms.lasthandoff: 02/24/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt
Wenn Sie das Objekt oder Steuerelement eine Schnittstelle hinzufügen, erstellen Sie in dieser Schnittstelle Stub-Out-Funktionen für jede Methode. Im Objekt oder Steuerelement können Sie nur Schnittstellen, die derzeit finden Sie in eine vorhandene Typbibliothek hinzufügen. Außerdem muss die Klasse, in dem Sie die Schnittstelle hinzufügen, Implementieren der [BEGIN_COM_MAP](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333) Makro oder, falls das Projekt attributiert ist, müssen die `coclass` Attribut.  
  
 Sie können eine neue Schnittstelle zu Ihrem Steuerelement auf zwei Arten hinzufügen: manuell oder mithilfe von Code-Assistenten in der Klassenansicht.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Code-Assistenten in der Klassenansicht mit eine Schnittstelle an ein vorhandenes Objekt oder ein Steuerelement hinzugefügt  
  
1.  In [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste des Klassennamen eines Steuerelements. Z. B. eine Vollzugriff oder zusammengesetzten Steuerelements oder eine beliebige andere Steuerelementklasse, die ein-Makro in ihrer Headerdatei implementiert.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Schnittstelle implementieren**.  
  
3.  Wählen Sie die Schnittstellen zum Implementieren der [Assistent zum Implementieren von Schnittstellen](../../ide/implement-interface-wizard.md). Wenn die Schnittstelle in keiner verfügbaren nicht vorhanden ist, müssen Sie dann Sie der IDL-Datei manuell hinzufügen.  
  
### <a name="to-add-a-new-interface-manually"></a>So fügen Sie eine neue Schnittstelle manuell hinzu  
  
1.  Fügen Sie die Definition der neuen Schnittstelle der IDL-Datei.  
  
2.  Leiten Sie das Objekt oder Steuerelement von der Schnittstelle.  
  
3.  Erstellen Sie ein neues [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) für die Schnittstelle, oder falls das Projekt attributiert ist, fügen Sie der `coclass` Attribut.  
  
4.  Implementieren Sie Methoden der Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)


