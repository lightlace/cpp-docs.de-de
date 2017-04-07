---
title: "Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt | Microsoft Docs"
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 10b252047a7bae1bbd54e854445dcd90db06a341
ms.lasthandoff: 03/31/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>Hinzufügen einer neuen Schnittstelle in einem ATL-Projekt
Wenn Sie eine Schnittstelle zu Ihrem Objekt oder ein Steuerelement hinzufügen, erstellen Sie in dieser Schnittstelle Stub-Out-Funktionen für die einzelnen Methoden. In Ihrem Objekt oder einem Steuerelement können Sie nur Schnittstellen aktuell in eine vorhandene Typbibliothek hinzufügen. Außerdem muss die Klasse, in dem Sie die Schnittstelle hinzufügen, implementieren die [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) Makro oder, falls das Projekt attributiert ist, muss die `coclass` Attribut.  
  
 Sie können eine neue Schnittstelle das Steuerelement auf zwei Arten hinzufügen: manuell oder mithilfe von Code-Assistenten in der Klassenansicht.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Code-Assistenten in der Klassenansicht mithilfe eine Schnittstelle an ein vorhandenes Objekt oder ein Steuerelement hinzufügen  
  
1.  In [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste des Klassennamen eines Steuerelements. Z. B. eine Vollzugriff oder zusammengesetztes Steuerelement oder jede andere Control-Klasse, die in der Headerdatei ein-Makro implementiert.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Schnittstelle implementieren**.  
  
3.  Wählen Sie die Schnittstellen zum Implementieren der [Assistent zum Implementieren von Schnittstellen](../../ide/implement-interface-wizard.md). Wenn die Schnittstelle in keiner verfügbaren nicht vorhanden ist, müssen dann Sie die IDL-Datei manuell hinzufügen.  
  
### <a name="to-add-a-new-interface-manually"></a>So fügen Sie eine neue Schnittstelle manuell hinzu  
  
1.  Fügen Sie die Definition der neuen Schnittstelle der IDL-Datei hinzu.  
  
2.  Leiten Sie das Objekt oder Steuerelement von der Schnittstelle.  
  
3.  Erstellen Sie ein neues [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) für die Schnittstelle oder wenn das Projekt attributiert ist, fügen Sie der `coclass` Attribut.  
  
4.  Implementieren Sie Methoden für die Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)


