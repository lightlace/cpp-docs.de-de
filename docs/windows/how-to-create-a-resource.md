---
title: 'Vorgehensweise: Erstellen einer Ressource | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [Visual Studio], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff08e42ac1afe3954b485e11ed6433449a6ee2ff
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571469"
---
# <a name="how-to-create-a-resource"></a>Gewusst wie: Erstellen einer Ressource
> [!NOTE]
>  Die Ressourcenansicht wird in Express-Editionen nicht unterstützt.  
  
### <a name="to-create-a-new-resource-in-resource-view"></a>So erstellen Sie eine neue Ressource in der Ressourcenansicht  
  
1.  Klicken Sie, während sich der Fokus in der [Ressourcenansicht](../windows/resource-view-window.md)befindet, auf das Menü **Bearbeiten** , und wählen Sie **Ressource hinzufügen** aus (oder klicken Sie mit der rechten Maustaste in der Ressourcenansicht auf die RC-Datei, und wählen Sie im Kontextmenü den Befehl **Ressource hinzufügen** aus).  
  
     **Hinweis** Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
### <a name="to-create-a-new-resource-in-solution-explorer"></a>So erstellen Sie eine neue Ressource im Projektmappen-Explorer  
  
1.  Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektordner, und wählen Sie **Hinzufügen**aus. Klicken Sie dann im Kontextmenü auf **Ressource hinzufügen** .  
  
     Wenn im Projekt noch keine RC-Datei vorhanden ist, wird mit diesem Schritt eine erstellt. Anschließend können Sie diesen Schritt wiederholen, um der neuen RC-Datei spezifische Ressourcentypen hinzuzufügen.  
  
2.  Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
### <a name="to-create-a-new-resource-in-class-view"></a>So erstellen Sie eine neue Ressource in der Klassenansicht  
  
1.  In [Klassenansicht](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925)mit der rechten Maustaste auf die Klasse, und wählen Sie **hinzufügen**, klicken Sie dann auf **Ressource hinzufügen** aus dem Kontextmenü.  
  
2.  Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.  
  
### <a name="to-create-a-new-resource-from-the-project-menu"></a>So erstellen Sie eine neue Ressource über das Menü "Projekt"  
  
1.  Wählen Sie im Menü **Projekt** den Befehl **Ressource hinzufügen**aus.  
  
 Wenn Sie eine neue Ressource erstellen, wird der Ressource von Visual C++ ein eindeutiger Name zugewiesen, z. B. "IDD_Dialog1". Sie können diese Ressourcen-ID anpassen, indem Sie die Ressourceneigenschaften entweder im zugehörigen Ressourcen-Editor oder im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)bearbeiten.  
  
 Eine Ressource kann entweder als neue Standardressource (die auf keiner Vorlage basiert) oder als Ressource erstellt werden, die von einer [Vorlage](../windows/how-to-use-resource-templates.md)erstellt wurde.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.*


## <a name="requirements"></a>Anforderungen  
  
Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editoren](../windows/resource-editors.md)   
 [Dialogfeld „Ressource hinzufügen“](../windows/add-resource-dialog-box.md)
