---
title: Klasse CMFCMaskedEdit | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
dev_langs:
- C++
helpviewer_keywords:
- CMFCMaskedEdit class
- CMFCMaskedEdit constructor
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 174551ecd75df8691d2a6086cbc074516f6d2045
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit-Klasse
Die `CMFCMaskedEdit` Klasse unterstützt ein maskiertes Bearbeitungssteuerelement, das Benutzereingaben anhand einer Maske überprüft und die überprüften Ergebnisse einer Vorlage entsprechend anzeigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Standardkonstruktor|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|Deaktiviert die Überprüfung von Benutzereingaben.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Gibt an, ob die `GetWindowText` -Methode ruft nur maskierte Zeichen ab.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|Initialisiert das maskierte edit-Steuerelement.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Gibt an, ob der MaskedEdit-Steuerelement bestimmte Gruppen von Benutzereingaben oder alle Benutzereingaben auswählt.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Gibt an, ob der Text überprüft wird, nur Zeichen maskiert, oder für die gesamte Maske.|  
|`CMFCMaskedEdit::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Ruft überprüft Text aus dem MaskedEdit-Steuerelement.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Gibt eine Zeichenfolge gültigen Zeichen, die der Benutzer eingeben kann.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Zeigt eine Meldung in der MaskedEdit-Steuerelement.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Aufgerufen, um das angegebene Zeichen für das entsprechende Maskenzeichen zu überprüfen.|  
  
## <a name="remarks"></a>Hinweise  
 Führen Sie die folgenden Schritte zur Verwendung der `CMFCMaskedEdit` Steuerelement in der Anwendung:  
  
 1. Einbetten einer `CMFCMaskedEdit` -Objekt in die Fensterklasse.  
  
 2. Rufen Sie die [CMFCMaskedEdit::EnableMask](#enablemask) Methode, um die Maske festzulegen.  
  
 3. Rufen Sie die [CMFCMaskedEdit::SetValidChars](#setvalidchars) Methode, um die Liste der gültigen Zeichen anzugeben.  
  
 4. Rufen Sie die [CMFCMaskedEdit::SetWindowText](#setwindowtext) -Methode an den Standardtext für die MaskedEdit-Steuerelement.  
  
 5. Rufen Sie die [CMFCMaskedEdit::GetWindowText](#getwindowtext) Methode zum Abrufen des Texts überprüft.  
  
 Wenn Sie eine oder mehrere Methoden zum Initialisieren der Maske, gültige Zeichen und Standardtext nicht aufrufen, verhält sich das MaskedEdit-Steuerelement einfach wie das standard-Edit-Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mithilfe einer Maske (z. B. eine Telefonnummer) einrichten der `EnableMask` Methode, um die Maske zu erstellen, für den MaskedEdit-Steuerelement, das `SetValidChars` Methode, um eine gültige Zeichenfolge anzugeben, die der Benutzer eingeben kann, und `SetWindowText` Methode eine Aufforderung angezeigt, in der maskierten Steuerelement bearbeiten. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#11;](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#12;](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmaskededit.h  
  
##  <a name="disablemask"></a>CMFCMaskedEdit::DisableMask  
 Deaktiviert die Überprüfung von Benutzereingaben.  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Validierung von Benutzereingaben deaktiviert ist, verhält sich der MaskedEdit-Steuerelement, wie die Standard-edit-Steuerelement.  
  
##  <a name="enablegetmaskedcharsonly"></a>CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 Gibt an, ob die `GetWindowText` -Methode ruft nur maskierte Zeichen ab.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um anzugeben, dass die [CMFCMaskedEdit::GetWindowText](#getwindowtext) Methode abrufen maskiert nur Zeichen; `FALSE` angeben, dass die Methode den gesamten Text abrufen. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um aktivieren maskierte Zeichen abgerufen werden sollen. Dann erstellen Sie ein maskiertes Bearbeitungssteuerelement, das die Telefonnummer an, z. B. (425) 555-0187 entspricht. Beim Aufrufen der `GetWindowText` -Methode wird die "4255550187" zurückgegeben. Abrufen von maskierte Zeichen durch Deaktivieren der `GetWindowText` -Methode gibt den Text, der in der Edit-Steuerelement, z. B. "(425) 555-0187" angezeigt wird.  
  
##  <a name="enablemask"></a>CMFCMaskedEdit::EnableMask  
 Initialisiert das maskierte edit-Steuerelement.  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszMask`  
 Eine Maskenzeichenfolge, die den Typ der Zeichen angibt, die an jeder Position in die Benutzereingabe angezeigt werden können. Die Länge der `lpszInputTemplate` und `lpszMask` Parameterzeichenfolgen müssen identisch sein. Finden Sie im Abschnitt "Hinweise" Weitere Informationen zu Maskenzeichen.  
  
 [in] `lpszInputTemplate`  
 Eine Maske Vorlagenzeichenfolge, die angibt, dass das Literal Zeichen kann an jeder Position in die Benutzereingabe angezeigt werden. Verwenden Sie den Unterstrich (_) als Platzhalter für ein Zeichen. Die Länge der `lpszInputTemplate` und `lpszMask` Parameterzeichenfolgen müssen identisch sein.  
  
 [in] `chMaskInputTemplate`  
 Ein Standardzeichen, die das Framework für jedes ungültige Zeichen in der Benutzereingabe ersetzt. Der Standardwert dieses Parameters ist Unterstrich (_).  
  
 [in] `lpszValid`  
 Eine Zeichenfolge, die einen Satz von gültigen Zeichen enthält. `NULL`Gibt an, dass alle Zeichen gültig sind. Der Standardwert dieses Parameters ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Maske für die MaskedEdit-Steuerelement zu erstellen. Leiten Sie eine Klasse von der `CMFCMaskedEdit` Klasse, und überschreiben die [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) Methode, um Ihren eigenen Code für die benutzerdefinierte Maske Verarbeitung verwenden.  
  
 Die folgende Tabelle listet die Maskenzeichen Standardwert:  
  
|Maskenzeichen|Definition|  
|--------------------|----------------|  
|D|Ziffer.|  
|T|Ziffer oder Leerzeichen.|  
|+|Plus ('+ ') minus ("-"), oder Leerzeichen.|  
|A|Alphabetisches Zeichen.|  
|c|Alphabetisches Zeichen oder Leerzeichen.|  
|A|Alphanumerisches Zeichen.|  
|a|Alphanumerisches Zeichen oder Leerzeichen.|  
|*|Ein druckbares Zeichen.|  
  
##  <a name="enableselectbygroup"></a>CMFCMaskedEdit::EnableSelectByGroup  
 Gibt an, ob der MaskedEdit-Steuerelement wählen bestimmte Gruppen Eingabe- oder alle Eingaben den Benutzer zulässt.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`nur Gruppen auszuwählen ist. `FALSE` auf den gesamten Text auszuwählen. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um anzugeben, ob der MaskedEdit-Steuerelement ermöglicht die einen Benutzer, Gruppe oder den gesamten Text auszuwählen.  
  
 Standardmäßig ist die Auswahl von Gruppe aktiviert. In diesem Fall kann der Benutzer nur fortlaufende Gruppen gültige Zeichen auswählen.  
  
 Sie können z. B. folgende MaskedEdit-Steuerelement verwenden, um eine Telefonnummer zu überprüfen:  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 Wenn die Auswahl von Gruppe aktiviert ist, kann der Benutzer nur "425", "555" oder "0187" Zeichenfolge Gruppen abrufen. Bei deaktiviertem Gruppenauswahl der Benutzer kann den gesamten Text der Telefonnummer abrufen: "(425) 555-0187".  
  
##  <a name="enablesetmaskedcharsonly"></a>CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 Gibt an, ob der Text für nur die maskierten Zeichen oder für die gesamte Maske überprüft wird.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`zur Überprüfung des Benutzers maskierten Eingabe gegen nur Zeichen; `FALSE` , mit die gesamte Maske überprüft. Der Standardwert ist `TRUE`.  
  
##  <a name="getwindowtext"></a>CMFCMaskedEdit::GetWindowText  
 Ruft überprüft Text aus dem MaskedEdit-Steuerelement.  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lpszStringBuf`  
 Ein Zeiger auf einen Puffer, der den Text in das Bearbeitungssteuerelement empfängt.  
  
 [in] `nMaxCount`  
 Die maximale Anzahl von Zeichen zu erhalten.  
  
 [out] `rstrString`  
 Ein Verweis auf das String-Objekt, das den Text von der Edit-Steuerelement empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste methodenüberladung gibt die Anzahl der Bytes der Zeichenfolge, die in kopiert wird die `lpszStringBuf` Parameterpuffer; 0, wenn der MaskedEdit-Steuerelement keinen Text enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Text aus dem MaskedEdit-Steuerelement auf die `lpszStringBuf` Puffer oder die `rstrString` Zeichenfolge.  
  
 Diese Methode definiert [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).  
  
##  <a name="ismaskedchar"></a>CMFCMaskedEdit::IsMaskedChar  
 Aufgerufen, um das angegebene Zeichen für das entsprechende Maskenzeichen zu überprüfen.  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `chChar`  
 Das Zeichen überprüft werden.  
  
 [in] `chMaskChar`  
 Das entsprechende Zeichen aus der Maskenzeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die `chChar` Parameter ist der Typ der von zugelassenen Zeichen der `chMaskChar` Parameter ist, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Eingabe nicht selbst überprüfen. Weitere Informationen zu Maskenzeichen, finden Sie unter der [CMFCMaskedEdit::EnableMask](#enablemask) Methode.  
  
##  <a name="setvalidchars"></a>CMFCMaskedEdit::SetValidChars  
 Gibt eine Zeichenfolge gültigen Zeichen, die der Benutzer eingeben kann.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszValid`  
 Eine Zeichenfolge, die die eingegebenen Zeichen enthält. `NULL`bedeutet, dass alle Zeichen zulässig sind. Der Standardwert dieses Parameters ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Liste der gültigen Zeichen definieren. Wenn ein Eingabezeichen nicht in dieser Liste enthalten ist, wird Sie MaskedEdit-Steuerelement nicht akzeptiert.  
  
 Im folgenden Codebeispiel wird akzeptiert nur hexadezimale Zahlen.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>CMFCMaskedEdit::SetWindowText  
 Zeigt eine Meldung in der MaskedEdit-Steuerelement.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszString`  
 Zeigt auf eine auf Null endende Zeichenfolge, die als Eingabeaufforderung verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt den Text des Steuerelements.  
  
 Diese Methode definiert [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)

