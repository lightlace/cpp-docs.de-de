---
title: 'Vorgehensweise: Hinzufügen von MFC-Unterstützung zu Ressourcenskriptdateien | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.add.MFC
dev_langs:
- C++
helpviewer_keywords:
- rc files, adding MFC support
- .rc files, adding MFC support
- MFC, adding support to resource scripts files
- resource script files, adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c0493e630c2b141da1fced6964ffc514c761d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-add-mfc-support-to-resource-script-files"></a>Gewusst wie: Hinzufügen von MFC-Unterstützung zu Ressourcenskriptdateien
In der Regel wird beim Erstellen einer MFC-Anwendung für die Verwendung von Windows die [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md), der Assistent generiert eine Reihe grundlegende Dateien (einschließlich einer Ressourcenskriptdatei (.rc)), die wichtigsten Funktionen der Microsoft Foundation enthält Klassen (MFC). Wenn Sie jedoch eine RC-Datei für eine Windows-Anwendung bearbeiten, die nicht auf MFC basiert, sind die folgenden, für die MFC-Grundstruktur spezifischen Funktionen nicht verfügbar:  
  
-   MFC-Code-Assistenten (zuvor namens "[MFC-Klassen-Assistent](http://msdn.microsoft.com/en-us/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)")  
  
-   Zeichenfolgen für Menüaufforderungen  
  
-   Auflisten der Inhalte von Kombinationsfeld-Steuerelementen  
  
-   Hosting von ActiveX-Steuerelementen  
  
 Vorhandenen RC-Dateien, die noch nicht über MFC-Unterstützung verfügen, kann diese jedoch hinzugefügt werden.  
  
### <a name="to-add-mfc-support-to-rc-files"></a>So fügen Sie RC-Dateien MFC-Unterstützung hinzu  
  
1.  Öffnen Sie die Ressourcenskriptdatei.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In [Ressourcenansicht](../windows/resource-view-window.md), markieren Sie den Ressourcenordner (z. B. MFC.rc).  
  
3.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)legen die **MFC Mode** Eigenschaft **"true"**.  
  
    > [!NOTE]
    >  Zusätzlich zum Festlegen dieses Flags muss auch gewährleistet sein, dass die RC-Datei Teil eines MFC-Projekts ist. Festlegen von z. B. nur **MFC Mode** auf **"true"** für eine RC-Datei in eine Win32-Projekt wird nicht erhalten Sie eine der MFC-Funktionen.  
  

  
 **Anforderungen**  
  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)