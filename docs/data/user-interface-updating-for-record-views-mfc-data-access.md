---
title: Benutzeroberflächen-Aktualisierung für Datensatzansichten (MFC-Datenzugriff)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: de94b28e713459edfd63aff832caecc7ea49ca33
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023359"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Benutzeroberflächen-Aktualisierung für Datensatzansichten (MFC-Datenzugriff)

`CRecordView` Stellt Standard-Benutzeroberflächen Aktualisierungshandler für die Navigationsbefehle bereit. Diese Handler automatisieren die Aktivierung und Deaktivierung der Benutzeroberflächenobjekte – Menüelemente und Symbolleisten-Schaltflächen. Der Anwendungs-Assistent stellt Standardmenüs bereit und, falls gewünscht die **andockbare Symbolleiste** verwenden, eine Reihe von Symbolleisten-Schaltflächen für die Befehle. Wenn Sie eine Datensatzansichtsklasse mithilfe von `CRecordView` erstellen, können Sie der Anwendung vergleichbare Benutzeroberflächenobjekte hinzufügen.

### <a name="to-create-menu-resources-with-the-menu-editor"></a>So erstellen Sie Menüressourcen mit dem Menü-Editor

1. Informieren Sie sich über die Verwendung der [Menü-Editor](../windows/menu-editor.md), erstellen Sie ein eigenes Menü mit denselben vier Befehlen.

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>So erstellen Sie Symbolleisten-Schaltflächen mit dem Grafik-Editor

1. Informieren Sie sich über die Verwendung der [Symbolleisten-Editor](../windows/toolbar-editor.md), bearbeiten Sie die Symbolleistenressource, um Symbolleisten-Schaltflächen für die Navigationsbefehle des Datensatzes hinzuzufügen.

## <a name="see-also"></a>Siehe auch

[Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)