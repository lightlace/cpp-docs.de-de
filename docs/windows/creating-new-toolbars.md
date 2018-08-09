---
title: Erstellen neuer Symbolleisten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor, creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c805fa46b47db5600dad153ffa51ba4f0b25442b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652294"
---
# <a name="creating-new-toolbars"></a>Erstellen neuer Symbolleisten
### <a name="to-create-a-new-toolbar"></a>Erstellen Sie eine neue Symbolleiste  
  
1.  In **Ressource** anzeigen, mit der rechten Maustaste in der RC-Datei, und wählen Sie dann **Ressource hinzufügen** aus dem Kontextmenü. (Wenn Sie eine vorhandene Symbolleiste in der RC-Datei verfügen, Sie können einfach mit der rechten Maustaste die **Symbolleiste** Ordner, und wählen **Toolbar einfügen** aus dem Kontextmenü.)  
  
     > [!NOTE]
     > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Symbolleiste** in die **Ressourcentyp** und dann auf **neu**.  
  
     Wenn ein Pluszeichen (**+**) wird neben der **Symbolleiste** Ressourcentyp an, es bedeutet, dass die Symbolleistenvorlagen verfügbar sind. Klicken Sie auf das Pluszeichen, um der Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und auf **neu**.  
  
     \- oder –  
  
3.  [Konvertieren eine vorhandene Bitmap auf einer Symbolleiste](../windows/converting-bitmaps-to-toolbars.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 MFC oder ATL  
  
## <a name="see-also"></a>Siehe auch  
 [Symbolleisten-Editor](../windows/toolbar-editor.md)