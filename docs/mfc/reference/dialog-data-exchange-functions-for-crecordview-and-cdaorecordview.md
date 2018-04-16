---
title: Dialogdatenaustausch Funktionen für CRecordView und CDaoRecordView | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f58b7ba7ae51c4db065cd7b30cc233128f7b7c68
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Dialogdatenaustausch-Funktionen für CRecordView und CDaoRecordView
Dieses Thema listet die DDX_Field-Funktionen, die zum Austausch von Daten zwischen einer [CRecordset](../../mfc/reference/crecordset-class.md) und ein [CRecordView](../../mfc/reference/crecordview-class.md) Formular oder ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) und ein [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Formular.  
  
> [!NOTE]
>  DDX_Field-Funktionen sind z. B. DDX-Funktionen, da sie exchange-Daten mit Steuerelementen in einem Formular. Aber im Gegensatz zu DDX, diese Daten mit den Feldern des zugehörigen Recordset-Objekt für die Sicht und nicht mit Feldern, die von der Datensatzansicht selbst austauschen. Weitere Informationen finden Sie unter Klassen `CRecordView` und `CDaoRecordView`.  
  
### <a name="ddxfield-functions"></a>DDX_Field-Funktionen  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Überträgt Ganzzahldaten zwischen einem Recordset-Felddatenmember und der Index der aktuellen Auswahl im Kombinationsfeld in einem [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|Übertragungen `CString` Feld mit dem Daten zwischen einem Recordset-Felddatenmember und das Steuerelement zum Bearbeiten eines Kombinationsfelds ein `CRecordView` oder `CDaoRecordView`. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das Element im Kombinationsfeld, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Übertragungen `CString` Feld mit dem Daten zwischen einem Recordset-Felddatenmember und das Steuerelement zum Bearbeiten eines Kombinationsfelds ein `CRecordView` oder `CDaoRecordView`. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das Element im Kombinationsfeld, das genau mit der angegebene Zeichenfolge übereinstimmt.|  
|[DDX_FieldCheck](#ddx_fieldcheck)|Überträgt boolesche Daten zwischen einem Recordset-Felddatenmember und ein Kontrollkästchen in einem `CRecordView` oder `CDaoRecordView`.|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Überträgt Ganzzahldaten zwischen einem Recordset-Felddatenmember und der Index der aktuellen Auswahl in einem Listenfeld in einem `CRecordView` oder `CDaoRecordView`.|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|Verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen einem Listenfeld-Steuerelement und den Felddatenmembern eines Recordset-Objekts. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das Element in der Liste, die mit den Zeichen in der angegebenen Zeichenfolge beginnt.|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Verwaltet die Übertragung von `CString` Daten zwischen einem Listenfeld-Steuerelement und den Felddatenmembern eines Recordset-Objekts. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das erste Element, das genau mit der angegebene Zeichenfolge übereinstimmt.|  
|[DDX_FieldRadio](#ddx_fieldradio)|Überträgt Ganzzahldaten zwischen einem Recordset-Felddatenmember und eine Gruppe von Optionsfeldern in einem `CRecordView` oder `CDaoRecordView`.|  
|[DDX_FieldScroll](#ddx_fieldscroll)|Legt fest oder ruft ab, das die Bildlaufposition des ein Bildlaufleisten-Steuerelement in einem `CRecordView` oder `CDaoRecordView`. Rufen Sie Ihre [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Funktion.|  
|[DDX_FieldSlider](#ddx_fieldslider)|Das Thumb-Position des Schieberegler-Steuerelements in einer Datensatzansicht synchronisiert und ein `int` Felddatenmember der Recordset. |
|[DDX_FieldText](#ddx_fieldtext)|Überladene Versionen stehen für die Übertragung von `int`, **"uint"**, **lange**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **"float"** , **doppelte**, **kurze**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), und [COleCurrency](../../mfc/reference/colecurrency-class.md) Daten zwischen einem Recordset-Felddatenmember und eine Bearbeitung Feld einem `CRecordView` oder `CDaoRecordView`.|  
  
##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex  
 Die `DDX_FieldCBIndex` Funktion wird den Index des ausgewählten Elements in das Listenfeld-Steuerelement von einem Kombinationsfeld-Steuerelement in einer Datensatzansicht synchronisiert und ein `int` Felddatenmember eines Recordsets der Datensatzansicht zugeordnet.  
  
```  
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *index*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die Auswahl im Steuerelement auf Grundlage des Werts im angegebenen *Index*. Für eine Übertragung vom Recordset an das Steuerelement das Recordset-Feld Null ist, MFC den Wert des Indexes festgelegt auf 0. Wenn das Steuerelement leer ist oder wenn kein Element ausgewählt ist, wird das Recordset-Feld in einer Übertragung der Steuerung zum Recordset auf 0 festgelegt.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Im Beispiel wäre für ähnlich `DDX_FieldCBIndex`.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString  
 Die `DDX_FieldCBString` -Funktion verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen den Edit-Steuerelement von einem Kombinationsfeld-Steuerelement in einer Datensatzansicht und ein `CString` Felddatenmember eines Recordsets der Datensatzansicht zugeordnet.  
  
```  
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die aktuelle Auswahl im Kombinationsfeld, um die erste Zeile, die mit den Zeichen im angegebenen Zeichenfolge beginnt *Wert*. Für eine Übertragung vom Recordset an das Steuerelement, wenn das Recordset-Feld Null ist, wird keine Auswahl im Kombinationsfeld entfernt und das Bearbeitungssteuerelement des Kombinationsfelds festgelegt ist leer. Für eine Übertragung von Control Recordset Wenn das Steuerelement leer ist, wird das Recordset-Feld auf Null festgelegt bei können das Feld.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Das Beispiel enthält einen Aufruf an `DDX_FieldCBString`.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact  
 Die `DDX_FieldCBStringExact` -Funktion verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen den Edit-Steuerelement von einem Kombinationsfeld-Steuerelement in einer Datensatzansicht und ein `CString` Felddatenmember eines Recordsets der Datensatzansicht zugeordnet.  
  
```  
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die aktuelle Auswahl im Kombinationsfeld, um die erste Zeile, die mit der angegebenen Zeichenfolge übereinstimmt *Wert*. Für eine Übertragung vom Recordset an das Steuerelement, wenn das Recordset-Feld NULL ist, wird keine Auswahl im Kombinationsfeld entfernt und im Bearbeitungsfeld des Kombinationsfelds festgelegt ist leer. Wenn das Steuerelement leer ist, ist das Recordset-Feld auf eine Übertragung von Control Recordset auf NULL festgelegt.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldCBStringExact` werden vergleichbar.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck  
 Die `DDX_FieldCheck` -Funktion verwaltet die Übertragung von `int` Daten zwischen einem Kontrollkästchen-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem `int` -Datenmember des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekt.  
  
```  
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID, der das Kontrollkästchensteuerelement die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *Wert*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_FieldCheck` aufgerufen wird, *Wert* mit dem aktuellen Status des Kontrollkästchen-Steuerelements festgelegt ist oder der Zustand des Steuerelements auf festgelegt ist *Wert*, je nachdem, auf die Richtung der Übertragung.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex  
 Die `DDX_FieldLBIndex` Funktion wird den Index des ausgewählten Elements in einem Listenfeld-Steuerelement in einer Datensatzansicht synchronisiert und ein `int` Felddatenmember eines Recordsets der Datensatzansicht zugeordnet.  
  
```  
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *index*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die Auswahl im Steuerelement auf Grundlage des Werts im angegebenen *Index*. Für eine Übertragung vom Recordset an das Steuerelement das Recordset-Feld Null ist, MFC den Wert des Indexes festgelegt auf 0. Wenn das Steuerelement leer ist, ist das Recordset-Feld auf eine Übertragung von Control Recordset auf 0 festgelegt.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString  
 Die `DDX_FieldLBString` kopiert die aktuelle Auswahl der ein Listenfeld-Steuerelement in einer Datensatzansicht auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Felddatenmember eines Recordsets der Datensatzansicht zugeordnet.  
  
```  
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 In umgekehrter Richtung, setzt diese Funktion die aktuelle Auswahl im Listenfeld auf die erste Zeile, die mit den Zeichen im angegebenen Zeichenfolge beginnt *Wert*. Das Recordset-Feld Null ist, wird keine Auswahl auf einer Übertragung vom Recordset an das Steuerelement aus dem Listenfeld entfernt. Wenn das Steuerelement leer ist, ist das Recordset-Feld auf eine Übertragung von Control Recordset auf Null festgelegt.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldLBString` werden vergleichbar.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact  
 Die `DDX_FieldLBStringExact` Funktion kopiert die aktuelle Auswahl der ein Listenfeld-Steuerelement in einer Datensatzansicht auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Felddatenmember eines Recordsets der Datensatzansicht zugeordnet.  
  
```  
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 In umgekehrter Richtung, setzt diese Funktion die aktuelle Auswahl im Listenfeld auf die erste Zeile, die mit der angegebenen Zeichenfolge übereinstimmt *Wert*. Das Recordset-Feld Null ist, wird keine Auswahl auf einer Übertragung vom Recordset an das Steuerelement aus dem Listenfeld entfernt. Wenn das Steuerelement leer ist, ist das Recordset-Feld auf eine Übertragung von Control Recordset auf Null festgelegt.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldLBStringExact` werden vergleichbar.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio  
 Die `DDX_FieldRadio` Funktion ordnet eine nullbasierte `int` Membervariable der einer Datensatzansicht Recordset mit den derzeit ausgewählten Optionsfelds in einer Gruppe von Optionsfeldern in der Datensatzansicht angezeigt.  
  
```  
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID des ersten in einer Gruppe (mit Format **WS_GROUP**) von benachbarten Optionsfeld-Steuerelementen in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie zur Ansicht aus dem Recordset-Feld zu übertragen, diese Funktion aktiviert die *n-te* Optionsfeld (nullbasiert) und deaktiviert die anderen Schaltflächen. In umgekehrter Richtung legt diese Funktion das Recordset-Feld die Ordinalzahl des Optionsfelds, der derzeit auf (aktivierten) befindet. Bei einer Übertragung vom Recordset an das Steuerelement wird das Recordset-Feld Null ist, keine Schaltfläche "ausgewählt. Für eine Übertragung von Control Recordset Wenn kein Steuerelement ausgewählt ist, wird das Recordset-Feld auf Null festgelegt, wenn die Felder, die zulässig sind.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldRadio` werden vergleichbar.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll  
 Die `DDX_FieldScroll` Funktion synchronisiert die Bildlaufposition des ein Bildlaufleisten-Steuerelement in einer Datensatzansicht und ein `int` Felddatenmember der Recordset der Datensatzansicht (oder die ganzzahlige Variable, die Sie auswählen, für die Zuordnung) zugeordnet ist.  
  
```  
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 *nIDC\*\*  
 Die ID des ersten in einer Gruppe (mit Format **WS_GROUP**) von benachbarten Optionsfeld-Steuerelementen in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die Bildlaufposition des Schiebeleisten-Steuerelements auf den Wert im angegebenen *Wert*. Das Recordset-Feld Null ist, wird das Bildlaufleisten-Steuerelement auf einer Übertragung vom Recordset an das Steuerelement auf 0 festgelegt. Auf einer Übertragung vom Steuerelement Recordset das Steuerelement leer ist, ist der Wert des Felds Recordset 0.  
  
 Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldScroll` werden vergleichbar.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>name="ddx_fieldslider"></a>  DDX_FieldSlider
Die `DDX_FieldSlider` Funktion synchronisiert die Thumb-Position des Schieberegler-Steuerelements in einer Datensatzansicht und ein `int` Felddatenmember der Recordset der Datensatzansicht (oder die ganzzahlige Variable, die Sie auswählen, für die Zuordnung) zugeordnet ist.  
   
### <a name="syntax"></a>Syntax  
  ```
   void AFXAPI DDX_FieldSlider(  
       CDataExchange* pDX,  
       int nIDC,  
       int& value,  
       CRecordset* pRecordset );  

void AFXAPI DDX_FieldSlider(  
     CDataExchange* pDX,  
     int nIDC,  
     int& value,  
     CDaoRecordset* pRecordset );  
```
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die Ressourcen-ID des Schieberegler-Steuerelements.  
  
 *Wert*  
 Ein Verweis auf den Wert ausgetauscht werden sollen. Dieser Parameter enthält oder wird verwendet, um das Schieberegler-Steuerelement aktuelle Thumb-Position festgelegt.  
  
 `pRecordset`  
 Ein Zeiger auf die zugeordnete `CRecordset` oder `CDaoRecordset` Objekt mit dem Daten ausgetauscht werden.  
   
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten vom Recordset zu den Schieberegler, setzt diese Funktion die Position des Schiebereglers auf den Wert im angegebenen *Wert*. Das Recordset-Feld Null ist, wird das Schieberegler-Steuerelement-Position auf einer Übertragung vom Recordset an das Steuerelement auf 0 festgelegt. Wenn das Steuerelement leer ist, ist der Wert des Felds Recordset auf eine Übertragung über das Steuerelement auf das Recordset 0.  
  
 `DDX_FieldSlider` Austausch Bereichsinformationen mit Schieberegler-Steuerelemente kann einfach eine Position, anstatt einen Bereich festlegen.  
  
 Verwenden Sie die erste Außerkraftsetzung der Funktion, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Außerkraftsetzung mit den DAO-basierten Klassen.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für `CRecordView` und `CDaoRecordView` Feldern finden Sie unter [Datensatzansichten](../../data/record-views-mfc-data-access.md). Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../using-csliderctrl.md).  
   
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldSlider` werden vergleichbar.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
  
##  <a name="ddx_fieldtext"></a>  DDX_FieldText  
 Die `DDX_FieldText` -Funktion verwaltet die Übertragung von `int`, **kurze**, **lange**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **"float"**, **doppelte**, **BOOL**, oder **BYTE** Daten zwischen einem Bearbeitungssteuerelement und den Felddatenmembern eines Recordset-Objekts.  
  
```  
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    UINT& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    short& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BOOL& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleDateTime& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleCurrency& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parameter  
 `pDX`  
 Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.  
  
 `nIDC`  
 Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *Wert*  
 Ein Verweis auf einen Feldmember für die Daten in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt. Der Datentyp des Werts abhängt, auf dem der überladenen Versionen der `DDX_FieldText` Sie verwenden.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden. This-Zeiger kann `DDX_FieldText` zu erkennen und Null-Werte festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Für [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte `DDX_FieldText` verwaltet auch die Übertragung von [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), und [COleCurrency](../../mfc/reference/colecurrency-class.md) Werte. Ein leeres Feld Bearbeitungssteuerelement gibt ein Null-Wert an. Auf eine Übertragung vom Recordset an das Steuerelement, wenn das Recordset-Feld Null ist, wird im Bearbeitungsfeld festgelegt ist leer. Wenn das Steuerelement leer ist, ist das Recordset-Feld auf eine Übertragung von Control Recordset auf Null festgelegt.  
  
 Verwenden Sie die Versionen mit [CRecordset](../../mfc/reference/crecordset-class.md) Parameter, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die Versionen mit [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Parameter, wenn Sie die DAO-basierten Klassen verwenden.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Die folgenden `DoDataExchange` für funktionsfähig sein, eine [CRecordView](../../mfc/reference/crecordview-class.md) enthält `DDX_FieldText` -Funktionsaufrufe für drei Datentypen: `IDC_COURSELIST` ist ein Kombinationsfeld; die anderen beiden Steuerelemente sind Bearbeitungsfelder. Für die DAO-Programmierung die *M_pSet* Parameter ist ein Zeiger auf eine [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 [!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
