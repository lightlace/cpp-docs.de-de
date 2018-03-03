---
title: CVSListBox-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
dev_langs:
- C++
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f97d55b0b23302920e71dfd35766bfa0a4294d97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cvslistbox-class"></a>CVSListBox-Klasse
Die `CVSListBox` Klasse unterstützt ein bearbeitbares Listensteuerelement.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|Erstellt ein `CVSListBox`-Objekt.|  
|`CVSListBox::~CVSListBox`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|Fügt eine Zeichenfolge um ein Listenfeld-Steuerelement. (Überschreibt `CVSListBoxBase::AddItem`.)|  
|[CVSListBox::EditItem](#edititem)|Startet einen Bearbeitungsvorgang an der Text eines Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::EditItem`.)|  
|[CVSListBox::GetCount](#getcount)|Ruft die Anzahl von Zeichenfolgen in ein bearbeitbares Listensteuerelement ab. (Überschreibt `CVSListBoxBase::GetCount`.)|  
|[CVSListBox::GetItemData](#getitemdata)|Ruft ab eine anwendungsspezifische 32-Bit-Wert, der ein bearbeitbares Listenelement-Steuerelement zugeordnet ist. (Überschreibt `CVSListBoxBase::GetItemData`.)|  
|[CVSListBox::GetItemText](#getitemtext)|Ruft den Text ein bearbeitbares Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::GetItemText`.)|  
|[CVSListBox::GetSelItem](#getselitem)|Ruft den nullbasierten Index des derzeit ausgewählten Elements in ein bearbeitbares Listensteuerelement ab. (Überschreibt `CVSListBoxBase::GetSelItem`.)|  
|`CVSListBox::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Weitere Informationen und Methodensyntax finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CVSListBoxBase::PreTranslateMessage`.)|  
|[CVSListBox::RemoveItem](#removeitem)|Entfernt ein Element aus der ein bearbeitbares Listensteuerelement. (Überschreibt `CVSListBoxBase::RemoveItem`.)|  
|[CVSListBox::SelectItem](#selectitem)|Wählt eine Liste Steuerzeichenfolge an. (Überschreibt `CVSListBoxBase::SelectItem`.)|  
|[CVSListBox::SetItemData](#setitemdata)|Ordnet einen anwendungsspezifische 32-Bit-Wert ein bearbeitbares Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::SetItemData`.)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|Gibt das Handle zum aktuellen eingebettete Listenansicht-Steuerelement zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CVSListBox` -Klasse bietet eine Reihe von Schaltflächen Bearbeiten, mit denen den Benutzer zu erstellen, ändern, löschen oder die Elemente in einem Listensteuerelement neu anordnen können.  
  
 Im folgenden finden ein Bild des Listensteuerelements bearbeitet werden. Der zweite Listeneintrag, der mit dem Titel "Element2" ist für die Bearbeitung ausgewählt.  
  
 ![CVSListBox-Steuerelement](../../mfc/reference/media/cvslistbox.png "Cvslistbox")  
  
 Wenn Sie den Ressourcen-Editor verwenden, um ein bearbeitbares Listensteuerelement hinzufügen, beachten Sie, dass die **Toolbox** Bereich des Editors bietet ein vordefinierte bearbeitbares Listensteuerelement. Fügen Sie ein statisches Steuerelement stattdessen, wie z. B. die **Gruppenfeld** Steuerelement. Das Framework verwendet die statische Steuerelement als Platzhalter an die Größe und Position des Steuerelements bearbeitet werden.  
  
 Um ein bearbeitbares Listensteuerelement in einer Dialogfeldvorlage verwenden, deklarieren einen `CVSListBox` Variable in Ihre Dialogfeldklasse. Um den Datenaustausch zwischen Variablen und das Steuerelement zu unterstützen, definieren eine `DDX_Control` Makro-Eintrag in der `DoDataExchange` Methode des Dialogfelds. Standardmäßig wird die bearbeitbares Listensteuerelement ohne bearbeiten Schaltflächen erstellt. Verwenden Sie die geerbte CVSListBoxBase::SetStandardButtons-Methode, um die Schaltflächen "Bearbeiten" aktiviert.  
  
 Weitere Informationen finden Sie im Verzeichnis "Samples" die `New Controls` -Beispieldateien, die Page3.cpp und Page3.h.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvslistbox.h  
  
##  <a name="additem"></a>CVSListBox::AddItem  
 Fügt eine Zeichenfolge um ein Listenfeld-Steuerelement.  
  
```  
virtual int AddItem(
    const CString& strIext,  
    DWORD_PTR dwData=0,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `strIext`  
 Ein Verweis auf eine Zeichenfolge.  
  
 [in] `dwData`  
 Eine anwendungsspezifische 32-Bit-Wert, der die Zeichenfolge zugeordnet ist. Der Standardwert ist 0.  
  
 [in] `iIndex`  
 Der nullbasierte Index der Position, die die Zeichenfolge enthalten soll. Wenn die `iIndex` Parameter ist-1, wird die Zeichenfolge am Ende der Liste hinzugefügt. Der Standardwert ist -1.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Position der Zeichenfolge im Listensteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CVSListBox::GetItemData](#getitemdata) Methode zum Abrufen des Werts, der von angegeben wird die `dwData` Parameter. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder ein Zeiger auf andere Daten sein.  
  
##  <a name="cvslistbox"></a>CVSListBox::CVSListBox  
 Erstellt ein `CVSListBox`-Objekt.  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="edititem"></a>CVSListBox::EditItem  
 Startet einen Bearbeitungsvorgang an der Text eines Listenelement-Steuerelement.  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Nullbasierten Index eines Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Bearbeitungsoperation wurde erfolgreich gestartet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer startet einen Bearbeitungsvorgang an, entweder durch Doppelklicken auf die Bezeichnung eines Elements oder durch Drücken der **F2** oder **LEERTASTE** Schlüssel, wenn ein Element den Fokus besitzt.  
  
##  <a name="getcount"></a>CVSListBox::GetCount  
 Ruft die Anzahl von Zeichenfolgen in ein bearbeitbares Listensteuerelement ab.  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listensteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Anzahl die eins größer als der Indexwert des letzten Elements ist, da der Index nullbasiert ist.  
  
##  <a name="getitemdata"></a>CVSListBox::GetItemData  
 Ruft ab eine anwendungsspezifische 32-Bit-Wert, der ein bearbeitbares Listenelement-Steuerelement zugeordnet ist.  
  
```  
virtual DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Die 32-Bit-Wert, der dem angegebenen Element zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CVSListBox::SetItemData](#setitemdata) oder [CVSListBox::AddItem](#additem) Methode, um die 32-Bit-Wert mit dem Listenelement-Steuerelement zuzuordnen. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder ein Zeiger auf andere Daten sein.  
  
##  <a name="getitemtext"></a>CVSListBox::GetItemText  
 Ruft den Text ein bearbeitbares Listenelement-Steuerelement.  
  
```  
virtual CString GetItemText(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Text des angegebenen Elements enthält.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlisthwnd"></a>CVSListBox::GetListHwnd  
 Gibt das Handle zum aktuellen eingebettete Listenansicht-Steuerelement zurück.  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das eingebettete Listenansicht-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um ein Handle für das eingebettete Listenansicht-Steuerelement abzurufen, die unterstützt die `CVSListBox` Klasse.  
  
##  <a name="getselitem"></a>CVSListBox::GetSelItem  
 Ruft den nullbasierten Index des derzeit ausgewählten Elements in ein bearbeitbares Listensteuerelement ab.  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn diese Methode erfolgreich ist, ist der nullbasierte Index des derzeit ausgewählten Elements; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removeitem"></a>CVSListBox::RemoveItem  
 Entfernt ein Element aus der ein bearbeitbares Listensteuerelement.  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das angegebene Element entfernt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="selectitem"></a>CVSListBox::SelectItem  
 Wählt eine Liste Steuerzeichenfolge an.  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iItem`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wählt das angegebene Element aus, und bei Bedarf, verschiebt das Element in der Ansicht.  
  
##  <a name="setitemdata"></a>CVSListBox::SetItemData  
 Ordnet einen anwendungsspezifische 32-Bit-Wert ein bearbeitbares Listenelement-Steuerelement.  
  
```  
virtual void SetItemData(
    int iIndex,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
 [in] `dwData`  
 Ein 32-Bit-Wert. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder ein Zeiger auf andere Daten sein.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
