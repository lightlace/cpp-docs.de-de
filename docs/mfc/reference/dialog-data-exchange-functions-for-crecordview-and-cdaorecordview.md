---
title: "Dialogdatenaustausch Funktionen für CRecordView und CDaoRecordView | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions
- ODBC [C++], dialog data exchange (DDX) support
- DDX (dialog data exchange) [C++], database support
- DDX (dialog data exchange) [C++], functions
- databases [C++], dialog data exchange (DDX) support
- DAO [C++], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 682c845aa2c915be69aee0d5e95f820573cd6084
ms.lasthandoff: 02/24/2017

---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Dialogdatenaustausch-Funktionen für CRecordView und CDaoRecordView
In diesem Thema die DDX_Field-Funktionen verwendet, um den Datenaustausch zwischen einer [CRecordset](../../mfc/reference/crecordset-class.md) und ein [CRecordView](../../mfc/reference/crecordview-class.md) Formular oder ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) und ein [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Form.  
  
> [!NOTE]
>  DDX_Field-Funktionen sind wie DDX-Funktionen, da sie exchange-Daten mit Steuerelementen in einem Formular. Aber im Gegensatz zu DDX, tauschen Daten mit den Feldern des zugehörigen Recordset-Objekt für die Ansicht anstatt mit der Datensatzansicht selbst. Weitere Informationen finden Sie unter Klassen `CRecordView` und `CDaoRecordView`.  
  
### <a name="ddxfield-functions"></a>DDX_Field-Funktionen  
  
|||  
|-|-|  
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Überträgt die ganzzahligen Daten zwischen einem Recordset-Felddatenmember und den Index der aktuellen Auswahl in einem Kombinationsfeld in einem [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|Überträgt `CString` Daten zwischen einem Recordset-Felddatenmember und das Steuerelement zum Bearbeiten eines Kombinationsfelds im Feld ein `CRecordView` oder `CDaoRecordView`. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das Element im Kombinationsfeld, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Überträgt `CString` Daten zwischen einem Recordset-Felddatenmember und das Steuerelement zum Bearbeiten eines Kombinationsfelds im Feld ein `CRecordView` oder `CDaoRecordView`. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das Element im Kombinationsfeld, das der angegebene Zeichenfolge genau übereinstimmt.|  
|[DDX_FieldCheck](#ddx_fieldcheck)|Überträgt boolesche Daten zwischen einem Recordset-Felddatenmember und ein Kontrollkästchen in einem `CRecordView` oder `CDaoRecordView`.|  
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Überträgt die ganzzahligen Daten zwischen einem Recordset-Felddatenmember und den Index der aktuellen Auswahl in einem Listenfeld in einem `CRecordView` oder `CDaoRecordView`.|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|Verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen einem Listenfeld-Steuerelement und den Felddatenmembern eines Recordset-Objekts. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das Element im Listenfeld, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Verwaltet die Übertragung von `CString` Daten zwischen einem Listenfeld-Steuerelement und den Felddatenmembern eines Recordset-Objekts. Beim Verschieben von Daten an das Steuerelement aus dem Recordset wählt diese Funktion das erste Element, das der angegebene Zeichenfolge genau übereinstimmt.|  
|[DDX_FieldRadio](#ddx_fieldradio)|Überträgt die ganzzahligen Daten zwischen einem Recordset-Felddatenmember und einer Gruppe von Optionsfeldern in einem `CRecordView` oder `CDaoRecordView`.|  
|[DDX_FieldScroll](#ddx_fieldscroll)|Legt fest oder ruft ab, das die Bildlaufposition des Bildlaufleisten-Steuerelements in einem `CRecordView` oder `CDaoRecordView`. Rufen Sie die [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Funktion.|  
|[DDX_FieldText](#ddx_fieldtext)|Überladene Versionen stehen für die Übertragung von `int`, **UINT**, **lang**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **Float**, **doppelte**, **kurze**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), und [COleCurrency](../../mfc/reference/colecurrency-class.md) Daten zwischen einem Recordset-Felddatenmember und bearbeiten im Feld ein `CRecordView` oder `CDaoRecordView`.|  
  
##  <a name="a-nameddxfieldcbindexa--ddxfieldcbindex"></a><a name="ddx_fieldcbindex"></a>DDX_FieldCBIndex  
 Die `DDX_FieldCBIndex` Funktion den Index des ausgewählten Elements im Listenfeld ein Kombinationsfeld-Steuerelements in einer Datensatzansicht synchronisiert und ein `int` Felddatenmember eines Recordsets, das mit der Datensatzansicht verknüpft ist.  
  
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
  
 *Index*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten aus dem Recordset auf das Steuerelement setzt diese Funktion die Auswahl im Steuerelement basierend auf dem Wert im angegebenen *Index*. Wenn das Recordset Feld Null ist, wird, setzt MFC auf eine Übertragung aus dem Recordset auf das Steuerelement den Wert für den Index auf 0. Wenn das Steuerelement leer ist oder wenn kein Element ausgewählt ist, wird das Recordset-Feld auf eine Übertragung vom Steuerelement Recordset auf 0 festgelegt.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Im Beispiel wäre ähnlich `DDX_FieldCBIndex`.  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  

##  <a name="a-nameddxfieldcbstringa--ddxfieldcbstring"></a><a name="ddx_fieldcbstring"></a>DDX_FieldCBString  
 Die `DDX_FieldCBString` Funktion verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen Bearbeitungssteuerelements ein Kombinationsfeld-Steuerelements in einer Datensatzansicht und ein `CString` Felddatenmember eines Recordsets, das mit der Datensatzansicht verknüpft ist.  
  
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
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten aus dem Recordset auf das Steuerelement setzt diese Funktion die aktuelle Auswahl im Kombinationsfeld auf die erste Zeile, die mit den Zeichen in der angegebenen Zeichenfolge in beginnt *Wert*. Eine Übertragung vom Recordset an das Steuerelement, wenn das Recordset Feld Null ist, wird eine Auswahl aus dem Kombinationsfeld entfernt und das Steuerelement zum Bearbeiten des Kombinationsfelds wird festgelegt, leer. Auf eine Übertragung vom Steuerelement Recordset Wenn das Steuerelement leer ist, wird das Recordset-Feld auf Null festgelegt, wenn das Feld ermöglicht.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Das Beispiel enthält einen Aufruf an `DDX_FieldCBString`.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
## <a name="a-nameddxfieldcbstringexacta--ddxfieldcbstringexact"></a><a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact  
 Die `DDX_FieldCBStringExact` Funktion verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen Bearbeitungssteuerelements ein Kombinationsfeld-Steuerelements in einer Datensatzansicht und ein `CString` Felddatenmember eines Recordsets, das mit der Datensatzansicht verknüpft ist.  
  
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
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten aus dem Recordset auf das Steuerelement setzt diese Funktion die aktuelle Auswahl im Kombinationsfeld auf die erste Zeile, die im angegebenen Zeichenfolge genau übereinstimmt *Wert*. Auf eine Übertragung vom Recordset an das Steuerelement, wenn das Recordset Feld NULL ist, wird eine Auswahl aus dem Kombinationsfeld entfernt und im Bearbeitungsfeld des Kombinationsfelds wird festgelegt, leer. Wenn das Steuerelement leer ist, wird das Recordset-Feld auf eine Übertragung vom Steuerelement Recordset auf NULL festgelegt.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldCBStringExact` wäre ähnlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldchecka--ddxfieldcheck"></a><a name="ddx_fieldcheck"></a>DDX_FieldCheck  
 Die `DDX_FieldCheck` Funktion verwaltet die Übertragung von `int` Daten zwischen einer Kontrollkästchen-Steuerelement in einem Dialogfeld bilden, Sicht oder Control-Objekt und ein `int` -Datenmember des Dialogfelds, Formularansicht oder Control-Objekt.  
  
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
 Die Ressourcen-ID des Kontrollkästchen-Steuerelements, das die Steuerelementeigenschaft zugeordnet werden soll.  
  
 *value*  
 Ein Verweis auf eine Membervariable des (Dialogfeld), in der Formularansicht oder Control View-Objekt, mit dem Daten ausgetauscht werden.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `DDX_FieldCheck` aufgerufen wird, *Wert* mit dem aktuellen Status des Kontrollkästchen-Steuerelements festgelegt ist oder der Zustand des Steuerelements auf *Wert*, abhängig von der Richtung der Übertragung.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldlbindexa--ddxfieldlbindex"></a><a name="ddx_fieldlbindex"></a>DDX_FieldLBIndex  
 Die `DDX_FieldLBIndex` Funktion den Index des ausgewählten Elements in einem Listenfeld-Steuerelement in einer Datensatzansicht synchronisiert und ein `int` Felddatenmember eines Recordsets, das mit der Datensatzansicht verknüpft ist.  
  
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
  
 *Index*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten aus dem Recordset auf das Steuerelement setzt diese Funktion die Auswahl im Steuerelement basierend auf dem Wert im angegebenen *Index*. Wenn das Recordset Feld Null ist, wird, setzt MFC auf eine Übertragung aus dem Recordset auf das Steuerelement den Wert für den Index auf 0. Wenn das Steuerelement leer ist, wird das Recordset-Feld auf eine Übertragung vom Steuerelement Recordset auf 0 festgelegt.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldlbstringa--ddxfieldlbstring"></a><a name="ddx_fieldlbstring"></a>DDX_FieldLBString  
 Die `DDX_FieldLBString` kopiert die aktuelle Auswahl des ein Listenfeld-Steuerelement in einer Datensatzansicht auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Felddatenmember eines Recordsets, das mit der Datensatzansicht verknüpft ist.  
  
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
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion legt die aktuelle Auswahl in umgekehrter Richtung wird im Listenfeld auf die erste Zeile, die mit den Zeichen in der angegebenen Zeichenfolge beginnt *Wert*. Wenn das Recordset Feld Null ist, wird die Auswahl auf eine Übertragung aus dem Recordset auf das Steuerelement aus dem Listenfeld entfernt. Wenn das Steuerelement leer ist, wird das Recordset-Feld auf eine Übertragung vom Steuerelement Recordset auf Null festgelegt.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldLBString` wäre ähnlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldlbstringexacta--ddxfieldlbstringexact"></a><a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact  
 Die `DDX_FieldLBStringExact` Funktion kopiert die aktuelle Auswahl des ein Listenfeld-Steuerelement in einer Datensatzansicht auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Felddatenmember eines Recordsets, das mit der Datensatzansicht verknüpft ist.  
  
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
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion legt die aktuelle Auswahl in umgekehrter Richtung wird im Listenfeld auf die erste Zeile, die im angegebenen Zeichenfolge genau übereinstimmt *Wert*. Wenn das Recordset Feld Null ist, wird die Auswahl auf eine Übertragung aus dem Recordset auf das Steuerelement aus dem Listenfeld entfernt. Wenn das Steuerelement leer ist, wird das Recordset-Feld auf eine Übertragung vom Steuerelement Recordset auf Null festgelegt.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldLBStringExact` wäre ähnlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldradioa--ddxfieldradio"></a><a name="ddx_fieldradio"></a>DDX_FieldRadio  
 Die `DDX_FieldRadio` Funktion ordnet ein nullbasiertes `int` Membervariablen einer Datensatzansicht Recordsets mit der aktuell ausgewählten Optionsfeld in einer Gruppe von Optionsfeldern in der Datensatzansicht angezeigt.  
  
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
 Die ID des ersten in einer Gruppe (stilvoll **WS_GROUP**) von benachbarten Optionsfeld-Steuerelementen in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Übertragung aus dem Recordset-Feld für die Ansicht von dieser Funktion wird die *te* Optionsfeld (nullbasiert) und deaktiviert die anderen Schaltflächen. In umgekehrter Richtung setzt diese Funktion das Recordset-Feld auf die Ordinalzahl des Optionsfelds, die derzeit auf (aktiviert) ist. Auf eine Übertragung aus dem Recordset auf das Steuerelement Wenn das Recordset Feld Null ist, wird ist keine Schaltfläche ausgewählt. Auf eine Übertragung vom Steuerelement Recordset Wenn kein Steuerelement ausgewählt ist, wird das Recordset-Feld auf Null festgelegt, wenn die Felder, die zulässig sind.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldRadio` wäre ähnlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldscrolla--ddxfieldscroll"></a><a name="ddx_fieldscroll"></a>DDX_FieldScroll  
 Die `DDX_FieldScroll` Funktion synchronisiert die Bildlaufposition des Bildlaufleisten-Steuerelements in einer Datensatzansicht und ein `int` Felddatenmember eines Recordsets, das mit der Datensatzansicht (oder beliebige ganzzahlige Variable, die Sie für die Zuordnung auswählen) zugeordnet ist.  
  
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
  
 *nIDC\**  
 Die ID des ersten in einer Gruppe (stilvoll **WS_GROUP**) von benachbarten Optionsfeld-Steuerelementen in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.  
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Beim Verschieben von Daten aus dem Recordset auf das Steuerelement setzt diese Funktion die Bildlaufposition des Schiebeleisten-Steuerelements im angegebenen Wert *Wert*. Wenn das Recordset Feld Null ist, ist das ScrollBar-Steuerelement auf einer Übertragung vom Recordset für das Steuerelement auf 0 festgelegt. Wenn das Steuerelement leer ist, ist der Wert des Felds Recordset auf eine Übertragung vom Steuerelement Recordset 0.  
  
 Verwenden Sie die erste Version, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldScroll` wäre ähnlich.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
  
##  <a name="a-nameddxfieldtexta--ddxfieldtext"></a><a name="ddx_fieldtext"></a>DDX_FieldText  
 Die `DDX_FieldText` Funktion verwaltet die Übertragung von `int`, **kurze**, **lang**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **Float**, **doppelte**, **BOOL**, oder **BYTE** Daten zwischen einem Bearbeitungssteuerelement und den Felddatenmembern eines Recordset-Objekts.  
  
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
  
 *value*  
 Ein Verweis auf einen Felddatenmember im zugeordneten `CRecordset` oder `CDaoRecordset` Objekt. Der Datentyp der Wert hängt von der überladenen Versionen der `DDX_FieldText` Sie verwenden.  
  
 `pRecordset`  
 Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt, mit denen Daten ausgetauscht werden. Dieser Zeiger ermöglicht `DDX_FieldText` erkennen und Null-Werte festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Für [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte `DDX_FieldText` verwaltet auch die Übertragung von [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), und [COleCurrency](../../mfc/reference/colecurrency-class.md) Werte. Ein leeres Edit-Steuerelement gibt einen Null-Wert an. Auf eine Übertragung aus dem Recordset auf das Steuerelement, wenn das Recordset Feld Null ist, wird das Eingabefeld festgelegt ist leer. Wenn das Steuerelement leer ist, wird das Recordset-Feld auf eine Übertragung vom Steuerelement Recordset auf Null festgelegt.  
  
 Verwenden Sie die Versionen mit [CRecordset](../../mfc/reference/crecordset-class.md) Parameter, wenn Sie mit der ODBC-basierten Klassen arbeiten. Verwenden Sie die Versionen mit [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Parameter, wenn Sie mit DAO-basierte Klassen arbeiten.  
  
 Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und-Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Beispiel  
 Die folgenden `DoDataExchange` -Funktion für eine [CRecordView](../../mfc/reference/crecordview-class.md) enthält `DDX_FieldText` Funktionsaufrufe für drei Datentypen: `IDC_COURSELIST` ist ein Kombinationsfeld; die anderen zwei Steuerelemente sind Bearbeitungsfelder. Für DAO-Programmierung der *M_pSet* -Parameter ist ein Zeiger auf eine [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 [!code-cpp[NVC_MFCDatabase&#43;](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdao.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

