---
title: CVSListBox-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CVSListBox
dev_langs:
- C++
helpviewer_keywords:
- CVSListBox::PreTranslateMessage method
- CVSListBox class
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4527249fc1a22a1db0623ea46954065fcbd071f4
ms.lasthandoff: 02/24/2017

---
# <a name="cvslistbox-class"></a>CVSListBox-Klasse
Die `CVSListBox` Klasse unterstützt ein bearbeitbares Listensteuerelement.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|Erstellt ein `CVSListBox`-Objekt.|  
|`CVSListBox::~CVSListBox`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|Fügt eine Zeichenfolge zu einem Listensteuerelement. (Überschreibt `CVSListBoxBase::AddItem`.)|  
|[CVSListBox::EditItem](#edititem)|Startet einen Bearbeitungsvorgang für den Text von einem Steuerelement ein Element. (Überschreibt `CVSListBoxBase::EditItem`.)|  
|[CVSListBox::GetCount](#getcount)|Ruft die Anzahl der Zeichenfolgen in ein bearbeitbares Listensteuerelement ab. (Überschreibt `CVSListBoxBase::GetCount`.)|  
|[CVSListBox::GetItemData](#getitemdata)|Ruft einen anwendungsspezifische 32-Bit-Wert, der ein bearbeitbares Listenelement-Steuerelement zugeordnet ist. (Überschreibt `CVSListBoxBase::GetItemData`.)|  
|[CVSListBox::GetItemText](#getitemtext)|Ruft den Text ein bearbeitbares Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::GetItemText`.)|  
|[CVSListBox::GetSelItem](#getselitem)|Ruft den nullbasierten Index des derzeit ausgewählten Elements in ein bearbeitbares Listensteuerelement ab. (Überschreibt `CVSListBoxBase::GetSelItem`.)|  
|`CVSListBox::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Weitere Informationen und Methodensyntax finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CVSListBoxBase::PreTranslateMessage`.)|  
|[CVSListBox::RemoveItem](#removeitem)|Entfernt ein Element aus ein bearbeitbares Listensteuerelement. (Überschreibt `CVSListBoxBase::RemoveItem`.)|  
|[CVSListBox::SelectItem](#selectitem)|Wählt eine Liste-Zeichenfolge an. (Überschreibt `CVSListBoxBase::SelectItem`.)|  
|[CVSListBox::SetItemData](#setitemdata)|Ordnet einen anwendungsspezifische 32-Bit-Wert ein bearbeitbares Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::SetItemData`.)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|Gibt das Handle auf die aktuelle eingebettete Listenansicht-Steuerelement zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CVSListBox` -Klasse stellt eine Reihe von Bearbeitungsschaltflächen, die dem Benutzer ermöglichen, erstellen, ändern, löschen oder neu anordnen der Elemente in einem Listensteuerelement.  
  
 Im folgenden Code wird ein Bild des Steuerelements bearbeitet werden. Die zweite Listeneintrag, der mit dem Titel "Element2" ist für die Bearbeitung ausgewählt.  
  
 ![CVSListBox-Steuerelement](../../mfc/reference/media/cvslistbox.png "Cvslistbox")  
  
 Wenn Sie den Ressourcen-Editor verwenden, ein bearbeitbares Listensteuerelement hinzufügen, beachten Sie, dass die **Toolbox** Bereich des Editors bietet kein vordefinierte bearbeitbares Listensteuerelement. Fügen Sie stattdessen ein statisches Steuerelement wie z. B. die **Gruppenfeld** Steuerelement. Das Framework verwendet die statische Steuerelement als Platzhalter zum Angeben der Größe und Position des Steuerelements bearbeitet werden.  
  
 Um ein bearbeitbares Listensteuerelement in einer Dialogfeldvorlage verwenden, deklarieren Sie eine `CVSListBox` -Variable in der Dialogfeldklasse. Um den Datenaustausch zwischen Variablen und das Steuerelement zu unterstützen, definieren ein `DDX_Control` Makro-Eintrag in die `DoDataExchange` Methode des Dialogfelds. Standardmäßig wird die bearbeitbares Listensteuerelement ohne Bearbeitungsschaltflächen erstellt. Verwenden Sie die geerbte CVSListBoxBase::SetStandardButtons-Methode, um die Bearbeitungsschaltflächen aktivieren.  
  
 Weitere Informationen finden Sie unter dem Verzeichnis Samples die `New Controls` zu erfassen, die Dateien Page3.cpp und Page3.h.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxvslistbox.h  
  
##  <a name="a-nameadditema--cvslistboxadditem"></a><a name="additem"></a>CVSListBox::AddItem  
 Fügt eine Zeichenfolge zu einem Listensteuerelement.  
  
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
 Der nullbasierte Index der Position, die die Zeichenfolge enthält. Wenn der `iIndex` Parameter ist&1;, wird die Zeichenfolge an das Ende der Liste hinzugefügt. Der Standardwert ist -1.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Position der Zeichenfolge im Listensteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CVSListBox::GetItemData](#getitemdata) Methode zum Abrufen des Werts, der durch angegeben ist die `dwData` Parameter. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder einen Zeiger auf andere Daten sein.  
  
##  <a name="a-namecvslistboxa--cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVSListBox::CVSListBox  
 Erstellt ein `CVSListBox`-Objekt.  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameedititema--cvslistboxedititem"></a><a name="edititem"></a>CVSListBox::EditItem  
 Startet einen Bearbeitungsvorgang für den Text von einem Steuerelement ein Element.  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Nullbasierte Index des Listenelements-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bearbeitungsvorgang erfolgreich gestartet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer startet einen Bearbeitungsvorgang durch Doppelklicken auf die Bezeichnung eines Elements, oder drücken Sie die **F2** oder **LEERTASTE** Schlüssel, wenn ein Element den Fokus besitzt.  
  
##  <a name="a-namegetcounta--cvslistboxgetcount"></a><a name="getcount"></a>CVSListBox::GetCount  
 Ruft die Anzahl der Zeichenfolgen in ein bearbeitbares Listensteuerelement ab.  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Listensteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die Anzahl größer als der Wert für das letzte Element ist, da der Index nullbasiert ist.  
  
##  <a name="a-namegetitemdataa--cvslistboxgetitemdata"></a><a name="getitemdata"></a>CVSListBox::GetItemData  
 Ruft einen anwendungsspezifische 32-Bit-Wert, der ein bearbeitbares Listenelement-Steuerelement zugeordnet ist.  
  
```  
virtual DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Der 32-Bit-Wert, der mit dem angegebenen Element zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CVSListBox::SetItemData](#setitemdata) oder [CVSListBox::AddItem](#additem) Methode, um das Steuerelement ein Element den 32-Bit-Wert zugeordnet. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder einen Zeiger auf andere Daten sein.  
  
##  <a name="a-namegetitemtexta--cvslistboxgetitemtext"></a><a name="getitemtext"></a>CVSListBox::GetItemText  
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
  
##  <a name="a-namegetlisthwnda--cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>CVSListBox::GetListHwnd  
 Gibt das Handle auf die aktuelle eingebettete Listenansicht-Steuerelement zurück.  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das eingebettete Listenansicht-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um ein Handle für das eingebettete Listenansicht-Steuerelement abzurufen, die unterstützt die `CVSListBox` Klasse.  
  
##  <a name="a-namegetselitema--cvslistboxgetselitem"></a><a name="getselitem"></a>CVSListBox::GetSelItem  
 Ruft den nullbasierten Index des derzeit ausgewählten Elements in ein bearbeitbares Listensteuerelement ab.  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn diese Methode erfolgreich ist, ist der nullbasierte Index des derzeit ausgewählten Elements; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremoveitema--cvslistboxremoveitem"></a><a name="removeitem"></a>CVSListBox::RemoveItem  
 Entfernt ein Element aus ein bearbeitbares Listensteuerelement.  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das angegebene Element entfernt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameselectitema--cvslistboxselectitem"></a><a name="selectitem"></a>CVSListBox::SelectItem  
 Wählt eine Liste-Zeichenfolge an.  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iItem`  
 Der nullbasierte Index des ein bearbeitbares Listenelement-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird das angegebene Element ausgewählt und bei Bedarf, Bildlauf des Elements in die Ansicht.  
  
##  <a name="a-namesetitemdataa--cvslistboxsetitemdata"></a><a name="setitemdata"></a>CVSListBox::SetItemData  
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
 Ein 32-Bit-Wert. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder einen Zeiger auf andere Daten sein.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

