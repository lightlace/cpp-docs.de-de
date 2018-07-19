---
title: Benutzeroberflächen-Aktualisierung für Datensatzansichten (MFC-Datenzugriff) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1227ba1fe0a14af7013109b336d1d60eda41137e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105815"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Benutzeroberflächen-Aktualisierung für Datensatzansichten (MFC-Datenzugriff)
`CRecordView` Stellt Benutzeroberflächen-Aktualisierungshandler für die Navigationsbefehle. Diese Handler automatisieren die Aktivierung und Deaktivierung der Benutzeroberflächenobjekte – Menüelemente und Symbolleisten-Schaltflächen. Der Anwendungs-Assistent stellt Standardmenüs bereit und, falls gewünscht die **andockbare Symbolleiste** verwenden, eine Reihe von Symbolleisten-Schaltflächen für die Befehle. Wenn Sie eine Datensatzansichtsklasse mithilfe von `CRecordView` erstellen, können Sie der Anwendung vergleichbare Benutzeroberflächenobjekte hinzufügen.  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>So erstellen Sie Menüressourcen mit dem Menü-Editor  
  
1.  Verweisen auf die Informationen zur Verwendung der [Menü-Editor](../windows/menu-editor.md), erstellen Sie ein eigenes Menü mit denselben vier Befehlen.  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>So erstellen Sie Symbolleisten-Schaltflächen mit dem Grafik-Editor  
  
1.  Verweisen auf die Informationen zur Verwendung der [Symbolleisten-Editor](../windows/toolbar-editor.md), bearbeiten Sie die Symbolleistenressource, um Symbolleisten-Schaltflächen für die Navigationsbefehle des Datensatzes hinzuzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)