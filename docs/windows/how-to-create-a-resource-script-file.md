---
title: 'Vorgehensweise: erstellen eine Ressourcenskriptdatei | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files, creating
- .rc files, creating
- resource script files, creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed35392180d0531133413a54ca2190ed65519546
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570573"
---
# <a name="how-to-create-a-resource-script-file"></a>Gewusst wie: Erstellen einer Ressourcenskriptdatei
> [!NOTE]
>  Der Ressourcen-Editor ist in Express-Editionen nicht verfügbar.  
>   
>  Diese Materialien beziehen sich auf Windows-Desktopanwendungen. Für Projekte in .NET-Sprachen werden keine Ressourcenskriptdateien verwendet. Weitere Informationen finden Sie unter [Ressourcendateien](../windows/resource-files-visual-studio.md).  
  
### <a name="to-create-a-new-resource-script-rc-file"></a>So erstellen Sie eine neue Ressourcenskriptdatei (RC-Datei)  
  
1.  Setzen Sie den Fokus auf den vorhandenen Projektordner in **Projektmappen-Explorer**, z. B. "MyProject".  
  
    > [!NOTE]
    >  Verwechseln Sie den Projektordner nicht mit dem Projektmappenordner im Projektmappen-Explorer. Wenn den Fokus verschieben, auf die **Lösung** -Ordner, Ihre Auswahl in der **neues Element hinzufügen** (Dialogfeld) (in Schritt 3) unterscheiden.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf den Ordner **Visual C++** , und wählen Sie dann **Ressourcendatei (.rc)** im rechten Bereich aus.  
  
4.  Geben Sie im Textfeld **Name** einen Namen für die Ressourcenskriptdatei ein, und klicken Sie dann auf **Öffnen**.  
  
 Sie können jetzt neue Ressourcen [erstellen](../windows/how-to-create-a-resource.md) und diese der RC-Datei hinzufügen.  
  
> [!NOTE]
>  Eine Ressourcenskriptdatei (.rc) kann nur in ein vorhandenes Projekt aufgenommen werden, das bereits in der Visual Studio-IDE geladen wurde. Es können keine eigenständige RC-Datei (außerhalb des Projekts) erstellt werden. [Ressourcenvorlagen](../windows/how-to-use-resource-templates.md) (RCT-Dateien) können jederzeit erstellt werden.


## <a name="requirements"></a>Anforderungen  
  
Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)
