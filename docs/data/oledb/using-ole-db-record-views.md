---
title: Mithilfe von OLE DB-Datensatzansichten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB record views
- COleDBRecordView class, overview
- rowsets, record views
- record views, record view objects
- OLE DB, record views
- MFC, record views
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6cebf8a1c1130a33ffd07e2d23d65c55a2a67b34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-ole-db-record-views"></a>Verwenden von OLE DB-Datensatzansichten
Wenn Sie OLE DB-Rowset-Daten in einer MFC-Anwendung anzeigen möchten, verwenden Sie die MFC-Klasse [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md). Ein Datensatzansichts-Objekt erstellt, von `COleDBRecordView` ermöglicht es Ihnen, die Datenbankdatensätze in Steuerelementen mit MFC anzuzeigen. Die Datensatzansicht ist ein Dialogfeld Formularansicht können Sie direkt zu einem OLE DB-Rowset-Objekt, das aus erstellten verbunden die `CRowset` Vorlagenklasse. Ein Handle für das Rowsetobjekt, das Abrufen ist einfach:  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 Die Ansicht zeigt die Felder der `CRowset` Objekt in das Dialogfeld-Steuerelemente. Die `COleDBRecordView` Objekt verwendet (Dialogfeld Data Exchange, DDX) und die Navigationsfunktionen `CRowset` (**MoveFirst**, `MoveNext`, `MovePrev`, und `MoveLast`) zum Automatisieren der Verschiebung von Daten zwischen den Steuerelementen auf dem Formular und die Felder des Rowsets. `COleDBRecordView` der nachverfolgt Position des Benutzers im Rowset, damit die Datensatzansicht aktualisieren kann, die Benutzeroberfläche und stellt eine [OnMove](../../mfc/reference/coledbrecordview-class.md#onmove) Methode zum Aktualisieren des aktuellen Datensatzes vor dem Wechsel in eine andere.  
  
 Sie können DDX-Funktionen mit **COleDbRecordView** Daten direkt aus der Datenbankrecordset abrufen und in einem Dialogfeldsteuerelement anzeigt. Verwenden Sie die **DDX_\***  Methoden (z. B. `DDX_Text`), und nicht die **DDX_Field\***  Funktionen (z. B. `DDX_FieldText`) mit **COleDbRecordView** .  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)   
 [COleDBRecordView-Klasse](../../mfc/reference/coledbrecordview-class.md)