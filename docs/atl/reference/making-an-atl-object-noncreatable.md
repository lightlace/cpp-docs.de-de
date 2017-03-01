---
title: Erstellen eines ATL-Objekts als nicht erstellbares | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: b812c2d4bfeb0663d62051c05829f25dc7139faf
ms.lasthandoff: 02/24/2017

---
# <a name="making-an-atl-object-noncreatable"></a>Erstellen eines ATL-Objekts als nicht erstellbares
Sie können die Attribute eines ATL-basierten COM-Objekts ändern, sodass das Objekt nicht direkt von ein Client erstellt werden kann. In diesem Fall wird das Objekt durch einen Methodenaufruf zurückgegeben wird, auf einem anderen Objekt anstatt direkt erstellt.  
  
### <a name="to-make-an-object-noncreatable"></a>Ein Objekt vornehmen.  
  
1.  Entfernen Sie die [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) für das Objekt. Wenn Sie das Objekt, das das Steuerelement jedoch registriert werden soll, ersetzen Sie mit [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1).  
  
2.  Hinzufügen der [Noncreatable](../../windows/noncreatable.md) -Attribut auf die Co-Klasse in der IDL-Datei. Zum Beispiel:  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)


