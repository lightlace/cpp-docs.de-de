---
title: CMFCMaskedEdit Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 985cd4011dbb1ea8ccad7cd40c81833dd5507f11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371796"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit-Klasse
Die `CMFCMaskedEdit` Klasse unterstützt ein maskiertes Bearbeitungssteuerelement, das Benutzereingaben anhand einer Maske überprüft und zeigt die überprüften Ergebnisse einer Vorlage entsprechend.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Standardkonstruktor|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|Deaktiviert das Validieren von Benutzereingaben.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Gibt an, ob die `GetWindowText` Methode ruft nur maskierte Zeichen ab.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|Der maskierten initialisiert edit-Steuerelement.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Gibt an, ob die MaskedEdit-Steuerelement bestimmte Gruppen von Benutzereingaben oder alle Benutzereingaben auswählt.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Gibt an, ob der Text für überprüft wird, nur Zeichen maskiert, oder für die gesamte Maske.|  
|`CMFCMaskedEdit::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Ruft überprüft Text aus dem MaskedEdit-Steuerelement.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Gibt eine Zeichenfolge von Zeichen, die der Benutzer eingeben kann.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Eine Aufforderung in MaskedEdit-Steuerelement angezeigt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Wird aufgerufen, durch das Framework das angegebene Zeichen für das entsprechende Maskenzeichen überprüft.|  
  
## <a name="remarks"></a>Hinweise  
 Führen Sie die folgenden Schritte zum Verwenden der `CMFCMaskedEdit` Steuerelement in der Anwendung:  
  
 1. Einbetten einer `CMFCMaskedEdit` Objekt in der Fensterklasse.  
  
 2. Rufen Sie die [CMFCMaskedEdit::EnableMask](#enablemask) Methode, um die Maske anzugeben.  
  
 3. Rufen Sie die [CMFCMaskedEdit::SetValidChars](#setvalidchars) Methode, um die Liste der gültigen Zeichen anzugeben.  
  
 4. Rufen Sie die [CMFCMaskedEdit::SetWindowText](#setwindowtext) Methode, um den Standardtext anzugeben, für die MaskedEdit-Steuerelement.  
  
 5. Rufen Sie die [CMFCMaskedEdit::GetWindowText](#getwindowtext) Methode, um den überprüften Text abzurufen.  
  
 Wenn Sie eine oder mehrere Methoden zum Initialisieren der Maske, gültige Zeichen und Standardtext nicht aufrufen, verhält sich das MaskedEdit-Steuerelement einfach wie das standard-Edit-Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Einrichten einer Maske (z. B. eine Telefonnummer) mithilfe der `EnableMask` Methode zum Erstellen der Maske für die MaskedEdit-Steuerelement, das `SetValidChars` Methode, um eine Zeichenfolge mit gültigen Zeichen, die der Benutzer eingeben kann, und anzugeben`SetWindowText` Methode, um eine Aufforderung angezeigt, in der maskierten edit-Steuerelement. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxmaskededit.h  
  
##  <a name="disablemask"></a>  CMFCMaskedEdit::DisableMask  
 Deaktiviert das Validieren von Benutzereingaben.  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Validierung von Benutzereingaben deaktiviert ist, verhält sich MaskedEdit-Steuerelement, z. B. der Standard-edit-Steuerelement.  
  
##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 Gibt an, ob die `GetWindowText` Methode ruft nur maskierte Zeichen ab.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` um anzugeben, dass die [CMFCMaskedEdit::GetWindowText](#getwindowtext) Methode abrufen maskiert nur Zeichen; `FALSE` um anzugeben, dass die Methode den gesamten Text abrufen. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um aktivieren maskierte Zeichen abgerufen werden sollen. Dann erstellen Sie ein maskiertes Bearbeitungssteuerelement, das die Telefonnummer, z. B. (425) 555-0187 entspricht. Beim Aufrufen der `GetWindowText` -Methode, wird die "4255550187" zurückgegeben. Wenn Sie deaktivieren maskierte Zeichen abgerufen werden sollen die `GetWindowText` Methodenrückgabe den Text, der in das Bearbeitungssteuerelement, z. B. "(425) 555-0187" angezeigt wird.  
  
##  <a name="enablemask"></a>  CMFCMaskedEdit::EnableMask  
 Der maskierten initialisiert edit-Steuerelement.  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszMask`  
 Eine Maskenzeichenfolge, die den Typ der Zeichen angibt, die an jede Position in die Benutzereingabe angezeigt werden können. Die Länge der `lpszInputTemplate` und `lpszMask` Parameterzeichenfolgen müssen identisch sein. Finden Sie im Abschnitt "Hinweise" Weitere Details zur Maskenzeichen ein.  
  
 [in] `lpszInputTemplate`  
 Eine Maske Vorlagenzeichenfolge, die angibt, dass das Literal Zeichen kann an jede Position in die Benutzereingabe angezeigt werden. Verwenden Sie der Unterstrich (_) als zeichenplatzhalter. Die Länge der `lpszInputTemplate` und `lpszMask` Parameterzeichenfolgen müssen identisch sein.  
  
 [in] `chMaskInputTemplate`  
 Ein Standardzeichen, die das Framework für jedes ungültige Zeichen in der Benutzereingabe ersetzt. Der Standardwert dieses Parameters ist Unterstrich ("_").  
  
 [in] `lpszValid`  
 Eine Zeichenfolge, die einen Satz von gültigen Zeichen enthält. `NULL` Gibt an, dass alle Zeichen gültig sind. Der Standardwert dieses Parameters ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Maske für das MaskedEdit-Steuerelement zu erstellen. Leiten Sie eine Klasse aus der `CMFCMaskedEdit` Klasse, und überschreiben die [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) Methode, um Ihren eigenen Code für die benutzerdefinierte Maske Verarbeitung verwenden.  
  
 Die folgende Tabelle listet die Standardzeichen Maske:  
  
|Maskenzeichen|Definition|  
|--------------------|----------------|  
|D|Ziffer.|  
|T|Ziffern oder Leerzeichen.|  
|+|Plus ('+ ') minus ("-"), oder Leerzeichen.|  
|C|Alphabetisches Zeichen.|  
|c|Alphabetisches Zeichen oder Leerzeichen.|  
|A|Alphanumerisches Zeichen.|  
|eine|Alphanumerisches Zeichen oder Leerzeichen.|  
|*|Ein anderes druckbares Zeichen.|  
  
##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup  
 Gibt an, ob die MaskedEdit-Steuerelement den Benutzer auf bestimmte für ausgewählte Benutzergruppen Eingabe- oder alle Eingaben zulässt.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` nur Gruppen auswählen; `FALSE` um den gesamten Text auszuwählen. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um anzugeben, ob MaskedEdit-Steuerelement ausgewählt Gruppe oder den gesamten Text ermöglicht.  
  
 Standardmäßig ist die Auswahl von Gruppe aktiviert. In diesem Fall kann der Benutzer nur fortlaufende Gruppen gültige Zeichen auswählen.  
  
 Beispielsweise können Sie die folgenden MaskedEdit-Steuerelement verwenden, um eine Telefonnummer zu überprüfen:  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 Auswahl von Gruppe aktiviert ist, kann der Benutzer nur "425", "555" oder "0187" Zeichenfolge-Gruppen abgerufen werden. Wenn Gruppenauswahl deaktiviert, wird der Benutzer kann den gesamten Text der Telefonnummer abrufen: "(425) 555-0187".  
  
##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 Gibt an, ob der Text für die nur die maskierten Zeichen oder für die gesamte Maske überprüft wird.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` So überprüfen Sie den Benutzer maskiert Eingabe anhand von nur Zeichen; `FALSE` die gesamte Maske überprüft. Der Standardwert ist `TRUE`.  
  
##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText  
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
 Ein Verweis auf das String-Objekt, das den Text von das Bearbeitungssteuerelement empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste methodenüberladung gibt die Anzahl der Bytes der Zeichenfolge, die in kopiert die `lpszStringBuf` Parameterpuffer; 0, wenn die MaskedEdit-Steuerelement keinen Text enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Text aus dem MaskedEdit-Steuerelement an die `lpszStringBuf` Puffer oder die `rstrString` Zeichenfolge.  
  
 Diese Methode definiert [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).  
  
##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar  
 Wird aufgerufen, durch das Framework das angegebene Zeichen für das entsprechende Maskenzeichen überprüft.  
  
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
 `TRUE` Wenn die `chChar` Parameter weist den Typ der Höchstzahl von Zeichen der `chMaskChar` Parameter ist, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Eingabezeichen selbst zu validieren. Weitere Informationen zu Formatzeichen, finden Sie unter der [CMFCMaskedEdit::EnableMask](#enablemask) Methode.  
  
##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars  
 Gibt eine Zeichenfolge von Zeichen, die der Benutzer eingeben kann.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszValid`  
 Eine Zeichenfolge, die den Satz von gültigen Eingabezeichen enthält. `NULL` bedeutet, dass alle Zeichen gültig sind. Der Standardwert dieses Parameters ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Liste der gültigen Zeichen zu definieren. Wenn eine Eingabezeichen nicht in dieser Liste enthalten ist, wird Sie MaskedEdit-Steuerelement nicht akzeptiert.  
  
 Im folgenden Codebeispiel wird akzeptiert nur hexadezimale Zahlen.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText  
 Eine Aufforderung in MaskedEdit-Steuerelement angezeigt.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszString`  
 Zeigt auf eine auf Null endende Zeichenfolge, die als Eingabeaufforderung verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt den Steuerelementtext fest.  
  
 Diese Methode definiert [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)
