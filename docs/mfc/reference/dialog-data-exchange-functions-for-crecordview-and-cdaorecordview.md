---
title: "Dialogdatenaustausch-Funktionen f&#252;r CRecordView und CDaoRecordView | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], Unterstützung für Dialogdatenaustausch (DDX)"
  - "Datenbanken [C++], Unterstützung für Dialogdatenaustausch (DDX)"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch) [C++], Datenbankunterstützung"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch) [C++], Funktionen"
  - "DDX_Field-Funktionen"
  - "ODBC [C++], Unterstützung für Dialogdatenaustausch (DDX)"
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Dialogdatenaustausch-Funktionen f&#252;r CRecordView und CDaoRecordView
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema führt die DDX\_Field\-Funktionen auf, die für den Datenaustausch zwischen [CRecordset](../../mfc/reference/crecordset-class.md) und einem [CRecordView](../../mfc/reference/crecordview-class.md) Formular oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) und ein [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Formular verwendet werden.  
  
> [!NOTE]
>  DDX\_Field\-Funktionen entsprechen insofern DDX\-Funktionen dass sie Daten mit Steuerelementen in einem Formular.  Im Gegensatz als DDX, diese Daten mit den Feldern des zugeordneten Recordset\-Objekts der Ansicht und nicht mit Feldern der Datensatzansicht selbst.  Weitere Informationen finden Sie Klassen `CRecordView` und `CDaoRecordView`.  
  
### DDX\_Field\-Funktionen  
  
|||  
|-|-|  
|[DDX\_FieldCBIndex](../Topic/DDX_FieldCBIndex.md)|Übergangsganzzahldaten zwischen einem Felddatenmember des Recordsets und den Index der aktuellen Auswahl in einem Kombinationsfeld in [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX\_FieldCBString](../Topic/DDX_FieldCBString.md)|Übergangs\- `CString` Daten zwischen einem Felddatenmember des Recordsets und dem Bearbeitungssteuerelement eines Kombinationsfelds in `CRecordView` oder `CDaoRecordView`.  Wenn diese Daten vom Recordset zum Steuerelement bewegt, wird diese Funktion das Element im Kombinationsfeld aus, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|  
|[DDX\_FieldCBStringExact](../Topic/DDX_FieldCBStringExact.md)|Übergangs\- `CString` Daten zwischen einem Felddatenmember des Recordsets und dem Bearbeitungssteuerelement eines Kombinationsfelds in `CRecordView` oder `CDaoRecordView`.  Wenn diese Daten vom Recordset zum Steuerelement bewegt, wird diese Funktion das Element im Kombinationsfeld aus, das exakt die angegebene Zeichenfolge passt.|  
|[DDX\_FieldCheck](../Topic/DDX_FieldCheck.md)|Übergangsboolesche Daten zwischen einem Felddatenmember des Recordsets und einem Kontrollkästchen in `CRecordView` oder `CDaoRecordView`.|  
|[DDX\_FieldLBIndex](../Topic/DDX_FieldLBIndex.md)|Übergangsganzzahldaten zwischen einem Felddatenmember des Recordsets und den Index der aktuellen Auswahl in einem Listenfeld in `CRecordView` oder `CDaoRecordView`.|  
|[DDX\_FieldLBString](../Topic/DDX_FieldLBString.md)|Verwaltet [CString](../../atl-mfc-shared/reference/cstringt-class.md) die Übertragung von Daten zwischen einem Listenfeld\-Steuerelement und den Felddatenmembern eines Recordsets.  Wenn diese Daten vom Recordset zum Steuerelement bewegt, wird diese Funktion das Element im Listenfeld aus, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|  
|[DDX\_FieldLBStringExact](../Topic/DDX_FieldLBStringExact.md)|Verwaltet die Übertragung von Daten zwischen einem `CString` Listenfeld\-Steuerelement und den Felddatenmembern eines Recordsets.  Wenn diese Daten vom Recordset zum Steuerelement bewegt, wird diese Funktion den ersten Punkt aus, der über genau die angegebene Zeichenfolge passt.|  
|[DDX\_FieldRadio](../Topic/DDX_FieldRadio.md)|Übergangsganzzahldaten zwischen einem Felddatenmember des Recordsets und einer Optionsfeldgruppe in `CRecordView` oder `CDaoRecordView`.|  
|[DDX\_FieldScroll](../Topic/DDX_FieldScroll.md)|Setzt oder ruft die Bildlaufposition eines Bildlaufleisten\-Steuerelements in `CRecordView` oder `CDaoRecordView` ab.  Aufruf der [DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)\-Funktion.|  
|[DDX\_FieldText](../Topic/DDX_FieldText.md)|Überladene Versionen sind für das Übertragen von `int`, **UINT**, **long**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **short**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) und [COleCurrency](../../mfc/reference/colecurrency-class.md) Daten zwischen einem Felddatenmember des Recordsets und ein Eingabefeld in `CRecordView` oder `CDaoRecordView` verfügbar.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)