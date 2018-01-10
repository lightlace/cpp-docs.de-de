---
title: "Benutzeroberflächen-Aktualisierung für Datensatzansichten (MFC-Datenzugriff) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68b013f3b1211c42ffc7355df73f47f6520fac1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Benutzeroberflächen-Aktualisierung für Datensatzansichten (MFC-Datenzugriff)
`CRecordView`Stellt Benutzeroberflächen-Aktualisierungshandler für die Navigationsbefehle. Diese Handler automatisieren die Aktivierung und Deaktivierung der Benutzeroberflächenobjekte – Menüelemente und Symbolleisten-Schaltflächen. Der Anwendungs-Assistent stellt Standardmenüs bereit und, falls gewünscht die **andockbare Symbolleiste** verwenden, eine Reihe von Symbolleisten-Schaltflächen für die Befehle. Wenn Sie eine Datensatzansichtsklasse mithilfe von `CRecordView` erstellen, können Sie der Anwendung vergleichbare Benutzeroberflächenobjekte hinzufügen.  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>So erstellen Sie Menüressourcen mit dem Menü-Editor  
  
1.  Verweisen auf die Informationen zur Verwendung der [Menü-Editor](../windows/menu-editor.md), erstellen Sie ein eigenes Menü mit denselben vier Befehlen.  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>So erstellen Sie Symbolleisten-Schaltflächen mit dem Grafik-Editor  
  
1.  Verweisen auf die Informationen zur Verwendung der [Symbolleisten-Editor](../windows/toolbar-editor.md), bearbeiten Sie die Symbolleistenressource, um Symbolleisten-Schaltflächen für die Navigationsbefehle des Datensatzes hinzuzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)