---
title: Dialogdatenaustausch Funktionen für CRecordView und CDaoRecordView | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 295e19d875585e0ea166dfce552866b8c1fc81b7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392267"
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>Dialogdatenaustausch-Funktionen für CRecordView und CDaoRecordView

Dieses Thema listet die DDX_Field-Funktionen, die zum Austauschen von Daten zwischen verwendet eine [CRecordset](../../mfc/reference/crecordset-class.md) und ein [CRecordView](../../mfc/reference/crecordview-class.md) Formular oder ein [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) und [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Formular.

> [!NOTE]
>  DDX_Field-Funktionen sind z. B. DDX-Funktionen, da sie exchange-Daten mit Steuerelementen in einem Formular. Aber im Gegensatz zu DDX, Daten mit den Feldern des zugehörigen Recordset-Objekt von der Ansicht und nicht mit der Datensatzansicht selbst Felder tauschen. Weitere Informationen finden Sie in Klassen `CRecordView` und `CDaoRecordView`.

### <a name="ddxfield-functions"></a>DDX_Field-Funktionen

|||
|-|-|
|[DDX_FieldCBIndex](#ddx_fieldcbindex)|Überträgt Ganzzahldaten zwischen einem Recordset-Felddatenmember und den Index der aktuellen Auswahl in einem Kombinationsfeld in einem [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|
|[DDX_FieldCBString](#ddx_fieldcbstring)|Übertragungen `CString` Daten zwischen einem Recordset-Felddatenmember und das Steuerelement zum Bearbeiten eines Kombinationsfelds Feld einem `CRecordView` oder `CDaoRecordView`. Beim Verschieben von Daten aus dem Recordset auf das Steuerelement wählt diese Funktion das Element im Kombinationsfeld, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Übertragungen `CString` Daten zwischen einem Recordset-Felddatenmember und das Steuerelement zum Bearbeiten eines Kombinationsfelds Feld einem `CRecordView` oder `CDaoRecordView`. Beim Verschieben von Daten aus dem Recordset auf das Steuerelement wählt diese Funktion das Element im Kombinationsfeld, das die angegebene Zeichenfolge genau übereinstimmt.|
|[DDX_FieldCheck](#ddx_fieldcheck)|Überträgt boolesche Daten zwischen einem Recordset-Felddatenmember und ein Kontrollkästchen in einem `CRecordView` oder `CDaoRecordView`.|
|[DDX_FieldLBIndex](#ddx_fieldlbindex)|Überträgt Ganzzahldaten zwischen einem Recordset-Felddatenmember und den Index der aktuellen Auswahl in einem Listenfeld in einem `CRecordView` oder `CDaoRecordView`.|
|[DDX_FieldLBString](#ddx_fieldlbstring)|Verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen einem Listenfeld-Steuerelement und den Felddatenmembern eines Recordset-Objekts. Beim Verschieben von Daten aus dem Recordset auf das Steuerelement wählt diese Funktion das Element im Listenfeld, das mit den Zeichen in der angegebenen Zeichenfolge beginnt.|
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Verwaltet die Übertragung von `CString` Daten zwischen einem Listenfeld-Steuerelement und den Felddatenmembern eines Recordset-Objekts. Beim Verschieben von Daten aus dem Recordset auf das Steuerelement wählt diese Funktion das erste Element, das die angegebene Zeichenfolge genau übereinstimmt.|
|[DDX_FieldRadio](#ddx_fieldradio)|Überträgt Ganzzahldaten zwischen einem Recordset-Felddatenmember und einer Gruppe von Optionsfeldern in einem `CRecordView` oder `CDaoRecordView`.|
|[DDX_FieldScroll](#ddx_fieldscroll)|Legt fest oder ruft die Bildlaufposition des ein Schiebeleisten-Steuerelement in einem `CRecordView` oder `CDaoRecordView`. Rufen Sie Ihre [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) Funktion.|
|[DDX_FieldSlider](#ddx_fieldslider)|Die Position Thumb-Steuerelement von einem Schieberegler-Steuerelement in einer Datensatzansicht synchronisiert und ein `int` Felddatenmember der Recordset. |
|[DDX_FieldText](#ddx_fieldtext)|Überladene Versionen stehen zur Verfügung, für die Übertragung von `int`, **UINT**, **lange**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **"float"** , **doppelte**, **kurze**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), und [COleCurrency](../../mfc/reference/colecurrency-class.md) Daten zwischen einem Recordset-Felddatenmember und eines Bearbeitungsvorgangs im Dialogfeld eine `CRecordView` oder `CDaoRecordView`.|

##  <a name="ddx_fieldcbindex"></a>  DDX_FieldCBIndex

Die `DDX_FieldCBIndex` Funktion wird den Index des ausgewählten Elements im Listenfeld-Steuerelements von einem Kombinationsfeld-Steuerelement in einer Datensatzansicht synchronisiert und ein `int` felddatenelement eines Recordsets, die mit der Datensatzansicht verknüpft ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*index*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die Auswahl im Steuerelement basierend auf dem Wert im angegebenen *Index*. Wenn das Recordset-Feld Null ist, setzt MFC auf eine Übertragung des Steuerelements aus dem Recordset den Wert des Indexes auf 0. Wenn das Steuerelement leer ist oder wenn kein Element ausgewählt ist, wird das Recordset-Feld auf einer Übertragung vom Steuerelement zum Recordset auf 0 festgelegt.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Im Beispiel wäre für ähnlich `DDX_FieldCBIndex`.

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

##  <a name="ddx_fieldcbstring"></a>  DDX_FieldCBString

Die `DDX_FieldCBString` Funktion verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen der Edit-Steuerelements, der ein Kombinationsfeld-Steuerelement in einer Datensatzansicht und `CString` felddatenelement eines Recordsets, die mit der Datensatzansicht verknüpft ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Beim Verschieben von Daten aus dem Recordset auf das Steuerelement legt diese Funktion die aktuelle Auswahl im Kombinationsfeld in die erste Zeile, die mit den Zeichen in der angegebenen Zeichenfolge beginnt *Wert*. Für eine Übertragung aus dem Recordset an das Steuerelement, wenn das Recordset-Feld Null ist, wird eine Auswahl aus dem Kombinationsfeld entfernt und das Bearbeitungssteuerelement des Kombinationsfelds wird festgelegt, leer. Für eine Übertragung von Control Recordset Wenn das Steuerelement leer ist, wird das Recordset-Feld auf Null festgelegt, wenn das Feld lässt.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Das Beispiel enthält einen Aufruf von `DDX_FieldCBString`.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

## <a name="ddx_fieldcbstringexact"></a>  DDX_FieldCBStringExact

Die `DDX_FieldCBStringExact` Funktion verwaltet die Übertragung von [CString](../../atl-mfc-shared/reference/cstringt-class.md) Daten zwischen der Edit-Steuerelements, der ein Kombinationsfeld-Steuerelement in einer Datensatzansicht und `CString` felddatenelement eines Recordsets, die mit der Datensatzansicht verknüpft ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Beim Verschieben von Daten aus dem Recordset auf das Steuerelement legt diese Funktion die aktuelle Auswahl im Kombinationsfeld in die erste Zeile, die der angegebenen Zeichenfolge genau übereinstimmt *Wert*. Für eine Übertragung aus dem Recordset an das Steuerelement, wenn das Recordset-Feld NULL ist, wird eine Auswahl aus dem Kombinationsfeld entfernt und im Bearbeitungsfeld des Kombinationsfelds wird festgelegt, leer. Wenn das Steuerelement leer ist, ist auf eine Übertragung von Control Recordset das Recordset-Feld auf NULL festgelegt.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldCBStringExact` sind.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="ddx_fieldcheck"></a>  DDX_FieldCheck

Die `DDX_FieldCheck` Funktion verwaltet die Übertragung von **Int** Daten zwischen einem Kontrollkästchen-Steuerelement in einem Dialogfeld, einem Formularansichts- oder steuerungsansichtsobjekts und einem **Int** -Datenmember des im Dialogfeld, in der Formularansicht oder -Steuerelement View-Objekt.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Kontrollkästchen-Steuerelements, das der Eigenschaft des Steuerelements zugeordnet werden soll.

*Wert*<br/>
Ein Verweis auf eine Membervariable des Dialogfelds, Formularansicht oder steuerungsansichtsobjekts, mit dem Daten ausgetauscht werden.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn `DDX_FieldCheck` aufgerufen wird, *Wert* festgelegt ist, mit dem aktuellen Status des Kontrollkästchen-Steuerelements, oder den Zustand des Steuerelements *Wert*, je nachdem, von der Richtung der Übertragung.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md).

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="ddx_fieldlbindex"></a>  DDX_FieldLBIndex

Die `DDX_FieldLBIndex` Funktion wird den Index des ausgewählten Elements in einem Listenfeld-Steuerelement in einer Datensatzansicht synchronisiert und ein **Int** felddatenelement eines Recordsets, die mit der Datensatzansicht verknüpft ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*index*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Beim Verschieben von Daten an das Steuerelement aus dem Recordset setzt diese Funktion die Auswahl im Steuerelement basierend auf dem Wert im angegebenen *Index*. Wenn das Recordset-Feld Null ist, setzt MFC auf eine Übertragung des Steuerelements aus dem Recordset den Wert des Indexes auf 0. Wenn das Steuerelement leer ist, wird das Recordset-Feld auf einer Übertragung vom Steuerelement zum Recordset auf 0 festgelegt.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="ddx_fieldlbstring"></a>  DDX_FieldLBString

Die `DDX_FieldLBString` kopiert die aktuelle Auswahl des ein Listenfeld-Steuerelement in einer Datensatzansicht auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) felddatenelement eines Recordsets, die mit der Datensatzansicht verknüpft ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Diese Funktion legt die aktuelle Auswahl in umgekehrter Richtung, in das Listenfeld auf der ersten Zeile, die mit den Zeichen im angegebenen Zeichenfolge beginnt *Wert*. Wenn das Recordset-Feld Null ist, wird eine Auswahl auf eine Übertragung aus dem Recordset auf das Steuerelement aus dem Listenfeld entfernt. Wenn das Steuerelement leer ist, ist auf eine Übertragung von Control Recordset das Recordset-Feld auf Null festgelegt.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldLBString` sind.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="ddx_fieldlbstringexact"></a>  DDX_FieldLBStringExact

Die `DDX_FieldLBStringExact` Funktion kopiert die aktuelle Auswahl des ein Listenfeld-Steuerelement in einer Datensatzansicht auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) felddatenelement eines Recordsets, die mit der Datensatzansicht verknüpft ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Diese Funktion legt die aktuelle Auswahl in umgekehrter Richtung, in das Listenfeld auf der ersten Zeile, die der angegebenen Zeichenfolge genau übereinstimmt *Wert*. Wenn das Recordset-Feld Null ist, wird eine Auswahl auf eine Übertragung aus dem Recordset auf das Steuerelement aus dem Listenfeld entfernt. Wenn das Steuerelement leer ist, ist auf eine Übertragung von Control Recordset das Recordset-Feld auf Null festgelegt.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldLBStringExact` sind.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="ddx_fieldradio"></a>  DDX_FieldRadio

Die `DDX_FieldRadio` Funktion ordnet ein nullbasiertes **Int** Membervariable einer Datensatzansicht Recordsets mit den derzeit ausgewählten Optionsfelds in einer Gruppe von Optionsfeldern in der Datensatzansicht angezeigt.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID des ersten in einer Gruppe (mit WS_GROUP-Stil) von benachbarten Optionsfeld-Steuerelemente in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Wenn für die Ansicht aus dem Recordset-Feld zu übertragen, diese Funktion aktiviert die *n-ten* Optionsfeld "(nullbasiert) und deaktiviert die anderen Schaltflächen. Diese Funktion legt die Recordset-Feld in umgekehrter Richtung wird die Ordinalzahl des Optionsfelds, das derzeit auf (aktiviert) fest. Bei einer Übertragung aus dem Recordset auf das Steuerelement, wenn das Recordset-Feld Null ist, wird keine Schaltfläche ausgewählt. Für die Übertragung von Steuerelement zu Recordsets Wenn kein Steuerelement ausgewählt ist, wird das Recordset-Feld auf Null festgelegt, wenn die Felder, die zulässig sind.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldRadio` sind.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

##  <a name="ddx_fieldscroll"></a>  DDX_FieldScroll

Die `DDX_FieldScroll` Funktion synchronisiert die Bildlaufposition des ein Schiebeleisten-Steuerelement in einer Datensatzansicht und **Int** felddatenelement eines Recordsets, die mit der Datensatzansicht (oder beliebige ganzzahlige Variable, die Sie auswählen, für die Zuordnung) zugeordnet ist .

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID des ersten in einer Gruppe (mit WS_GROUP-Stil) von benachbarten Optionsfeld-Steuerelemente in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Beim Verschieben von Daten aus dem Recordset auf das Steuerelement legt diese Funktion die Bildlaufposition des Schiebeleisten-Steuerelements im angegebenen Wert *Wert*. Wenn das Recordset-Feld Null ist, ist auf eine Übertragung des Steuerelements aus dem Recordset Schiebeleisten-Steuerelements auf 0 festgelegt. Wenn das Steuerelement leer ist, ist der Wert des Felds Recordset auf eine Übertragung von Control Recordset 0.

Verwenden Sie die erste Version aus, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die zweite Version aus, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldScroll` sind.

### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>name="ddx_fieldslider"></a>  DDX_FieldSlider
Die `DDX_FieldSlider` Funktion wird die Position Thumb-Steuerelement von einem Schieberegler-Steuerelement in einer Datensatzansicht synchronisiert und ein **Int** felddatenelement eines Recordsets, die mit der Datensatzansicht (oder beliebige ganzzahlige Variable, die Sie auswählen, für die Zuordnung) zugeordnet ist.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die Ressourcen-ID des Schieberegler-Steuerelements.

*Wert*<br/>
Ein Verweis auf den Wert ausgetauscht werden sollen. Dieser Parameter enthält, oder wird verwendet, um die aktuelle Thumb-Position des Schieberegler-Steuerelements festgelegt.

*pRecordset*<br/>
Ein Zeiger auf das zugeordnete `CRecordset` oder `CDaoRecordset` Objekt mit dem Daten ausgetauscht werden.

### <a name="remarks"></a>Hinweise

Beim Verschieben von Daten aus dem Recordset für den Slider legt diese Funktion die Position des Schiebereglers auf den Wert im angegebenen *Wert*. Wenn das Recordset-Feld Null ist, ist das Schieberegler-Steuerelement Position auf eine Übertragung des Steuerelements aus dem Recordset auf 0 festgelegt. Wenn das Steuerelement leer ist, ist der Wert des Felds Recordset auf eine Übertragung über das Steuerelement das Recordset 0.

`DDX_FieldSlider` Bereichsinformationen mit Schieberegler-Steuerelemente kann eine Position, statt eines Bereichs ist nicht eintauschen.

Verwenden Sie beim ersten Überschreiben der Funktion, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie beim zweiten überschreiben, mit der DAO-basierte Klassen.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für `CRecordView` und `CDaoRecordView` Feldern finden Sie unter [Datensatzansichten](../../data/record-views-mfc-data-access.md). Weitere Informationen über Schieberegler-Steuerelemente finden Sie unter [Verwenden von CSliderCtrl](../using-csliderctrl.md).

### <a name="example"></a>Beispiel

Finden Sie unter [DDX_FieldText](#ddx_fieldtext) für ein allgemeines DDX_Field-Beispiel. Aufrufe von `DDX_FieldSlider` sind.

### <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

### <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)

##  <a name="ddx_fieldtext"></a>  DDX_FieldText

Die `DDX_FieldText` Funktion verwaltet die Übertragung von **Int**, **kurze**, **lange**, DWORD-Wert [CString](../../atl-mfc-shared/reference/cstringt-class.md), **"float"**, **doppelte**, **"bool"**, oder **BYTE** Daten zwischen einem Steuerelement mit Eingabefeld und den Felddatenmembern eines Recordset-Objekts.

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

*pDX*<br/>
Ein Zeiger auf eine [CDataExchange](../../mfc/reference/cdataexchange-class.md) Objekt. Das Framework stellt dieses Objekt bereit, um den Kontext des Datenaustauschs herzustellen, darunter seine Richtung.

*nIDC*<br/>
Die ID eines Steuerelements in der [CRecordView](../../mfc/reference/crecordview-class.md) oder [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Objekt.

*Wert*<br/>
Ein Verweis auf ein Felddatenmember in der zugeordneten `CRecordset` oder `CDaoRecordset` Objekt. Der Datentyp des Werts hängt vom verwendeten der überladenen Versionen der `DDX_FieldText` Sie verwenden.

*pRecordset*<br/>
Ein Zeiger auf die [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt mit dem Daten ausgetauscht werden. This-Zeiger kann `DDX_FieldText` zu erkennen und Null-Werte festgelegt.

### <a name="remarks"></a>Hinweise

Für [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte `DDX_FieldText` verwaltet auch die Übertragung von [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), und [COleCurrency](../../mfc/reference/colecurrency-class.md) Werte. Ein Steuerelement mit leeren Eingabefeld gibt einen Null-Wert an. Für eine Übertragung aus dem Recordset auf das Steuerelement, wenn das Recordset-Feld Null ist, wird das Eingabefeld festgelegt ist leer. Wenn das Steuerelement leer ist, ist auf eine Übertragung von Control Recordset das Recordset-Feld auf Null festgelegt.

Verwenden Sie die Versionen mit [CRecordset](../../mfc/reference/crecordset-class.md) Parameter, wenn Sie die ODBC-basierten Klassen verwenden. Verwenden Sie die Versionen mit [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Parameter, wenn Sie die DAO-basierten Klassen verwenden.

Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch und Validierung](../../mfc/dialog-data-exchange-and-validation.md). Beispiele und Weitere Informationen über DDX für [CRecordView](../../mfc/reference/crecordview-class.md) und [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) Feldern finden Sie im Artikel [Datensatzansichten](../../data/record-views-mfc-data-access.md).

### <a name="example"></a>Beispiel

Die folgenden `DoDataExchange` für funktionsfähig sein, eine [CRecordView](../../mfc/reference/crecordview-class.md) enthält `DDX_FieldText` Funktionsaufrufe für drei Datentypen: `IDC_COURSELIST` ist ein Kombinationsfeld; die anderen beiden Steuerelemente sind Bearbeitungsfelder. Für die DAO-Programmierung, die *M_pSet* Parameter ist ein Zeiger auf eine [CRecordset](../../mfc/reference/crecordset-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

[!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]


### <a name="requirements"></a>Anforderungen

  **Header** afxdao.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
