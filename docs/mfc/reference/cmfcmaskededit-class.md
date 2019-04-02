---
title: CMFCMaskedEdit-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: c1dcf89811fa5225283cb5bec120d3bd2fdfb003
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773787"
---
# <a name="cmfcmaskededit-class"></a>CMFCMaskedEdit-Klasse

Die `CMFCMaskedEdit` Klasse unterstützt ein maskiertes Bearbeitungssteuerelement, das Benutzereingaben anhand einer Maske überprüft und die überprüften Ergebnisse einer Vorlage entsprechend angezeigt.

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
|[CMFCMaskedEdit::DisableMask](#disablemask)|Deaktiviert die Überprüfung von Benutzereingaben.|
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Gibt an, ob die `GetWindowText` -Methode ruft nur maskierte Zeichen ab.|
|[CMFCMaskedEdit::EnableMask](#enablemask)|Initialisiert die maskiertes Bearbeitungssteuerelement.|
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Gibt an, ob das MaskedEdit-Steuerelement bestimmte Gruppen von Benutzereingaben oder alle Benutzereingaben auswählt.|
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Gibt an, ob der Text für überprüft wird, nur Zeichen maskiert wurde, oder für die gesamte Maske.|
|`CMFCMaskedEdit::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Ruft überprüft Text aus dem MaskedEdit-Steuerelement.|
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Gibt eine Zeichenfolge gültigen Zeichen, die der Benutzer eingeben kann.|
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Sie werden aufgefordert, in der MaskedEdit-Steuerelement.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Wird aufgerufen, durch das Framework, um das angegebene Zeichen mit dem entsprechenden Maskenzeichen zu überprüfen.|

## <a name="remarks"></a>Hinweise

Führen Sie die folgenden Schritte zur Verwendung der `CMFCMaskedEdit` Steuerelement in der Anwendung:

1. Einbetten einer `CMFCMaskedEdit` Objekt in Ihrem Fensterklasse.

2. Rufen Sie die [CMFCMaskedEdit::EnableMask](#enablemask) Methode, um die Maske anzugeben.

3. Rufen Sie die [CMFCMaskedEdit::SetValidChars](#setvalidchars) Methode, um die Liste der gültigen Zeichen anzugeben.

4. Rufen Sie die [CMFCMaskedEdit::SetWindowText](#setwindowtext) Methode, um den Standardtext anzugeben, für den MaskedEdit-Steuerelement.

5. Rufen Sie die [CMFCMaskedEdit::GetWindowText](#getwindowtext) Methode, um den überprüften Text nicht abrufen.

Wenn Sie eine oder mehrere Methoden zum Initialisieren die Mask, gültige Zeichen und Text standardmäßig nicht aufrufen, verhält sich der MaskedEdit-Steuerelement, genauso das standard-Edit-Steuerelement verhält sich.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Einrichten einer Maske (z. B. eine Telefonnummer) mithilfe der `EnableMask` Methode zum Erstellen der Maske für den MaskedEdit-Steuerelement, das `SetValidChars` Methode zum Angeben einer gültigen Zeichen, die der Benutzer eingeben kann und `SetWindowText` Methode, um eine Eingabeaufforderung angezeigt, in der maskierten Steuerelement bearbeiten. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../overview/visual-cpp-samples.md).

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

Deaktiviert die Überprüfung von Benutzereingaben.

```
void DisableMask();
```

### <a name="remarks"></a>Hinweise

Wenn die Validierung von Benutzereingaben deaktiviert ist, verhält sich so MaskedEdit-Steuerelement, wie der Standard-edit-Steuerelement.

##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly

Gibt an, ob die `GetWindowText` -Methode ruft nur maskierte Zeichen ab.

```
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] "True", die angeben, dass die [CMFCMaskedEdit::GetWindowText](#getwindowtext) Methode abrufen maskiert nur Zeichen. "False", um anzugeben, dass die Methode den gesamten Text abrufen. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Aktivieren der maskierte Zeichen abgerufen werden sollen. Dann erstellen Sie ein maskiertes Bearbeitungssteuerelement, das die Telefonnummer an, wie z. B. (425) 555-0187 entspricht. Wenn Sie beim Aufrufen der `GetWindowText` -Methode gibt "4255550187". Wenn Sie das Abrufen von maskierte Zeichen Deaktivieren der `GetWindowText` Methode gibt den Text zurück, die in das Bearbeitungssteuerelement, z. B. "(425) 555-0187" angezeigt wird.

##  <a name="enablemask"></a>  CMFCMaskedEdit::EnableMask

Initialisiert die maskiertes Bearbeitungssteuerelement.

```
void EnableMask(
    LPCTSTR lpszMask,
    LPCTSTR lpszInputTemplate,
    TCHAR chMaskInputTemplate=_T('_'),
    LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parameter

*lpszMask*<br/>
[in] Eine Maskenzeichenfolge, die den Typ von Zeichen angibt, die an jede Position in der Benutzereingabe angezeigt werden können. Die Länge der *LpszInputTemplate* und *LpszMask* Parameterzeichenfolgen müssen identisch sein. Finden Sie im Abschnitt "Hinweise" Weitere Informationen zu Zeichen maskiert.

*lpszInputTemplate*<br/>
[in] Eine Maske Vorlagenzeichenfolge, die angibt, dass das Literal Zeichen kann an jeder Position in der Benutzereingabe angezeigt werden. Verwenden Sie den Unterstrich ("_") als zeichenplatzhalter ein. Die Länge der *LpszInputTemplate* und *LpszMask* Parameterzeichenfolgen müssen identisch sein.

*chMaskInputTemplate*<br/>
[in] Ein Standardzeichen, die das Framework für jedes ungültige Zeichen in der Benutzereingabe ersetzt. Der Standardwert dieses Parameters ist Unterstrich ("_").

*lpszValid*<br/>
[in] Eine Zeichenfolge, die einen Satz von gültigen Zeichen enthält. NULL gibt an, dass alle Zeichen gültig sind. Der Standardwert dieses Parameters ist NULL.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die Maske für den MaskedEdit-Steuerelement zu erstellen. Leiten Sie eine Klasse aus der `CMFCMaskedEdit` Klasse, und überschreiben die [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) Methode, um Ihren eigenen Code für die benutzerdefinierte Maske Verarbeitung verwenden.

Die folgende Tabelle listet die Standard-Maskenzeichen:

|Maskenzeichen|Definition|
|--------------------|----------------|
|D|Ziffer.|
|T|Ziffern oder Leerzeichen.|
|+|Pluszeichen ('+ ') minus ("-"), oder Leerzeichen.|
|C|Alphabetisches Zeichen.|
|c|Alphabetisches Zeichen oder Leerzeichen.|
|A|Alphanumerisches Zeichen.|
|eine|Alphanumerische Zeichen oder Leerzeichen.|
|*|Ein druckbares Zeichen.|

##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup

Gibt an, ob das MaskedEdit-Steuerelement den Benutzer auf bestimmte Gruppen Eingabe- oder alle Eingaben zulässt.

```
void EnableSelectByGroup(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] "True", um nur Gruppen auszuwählen; "False", um den gesamten Text auszuwählen. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um anzugeben, ob das MaskedEdit-Steuerelement ein Benutzer nach Gruppe oder den gesamten Text auswählen kann.

Standardmäßig ist die Auswahl nach Gruppe aktiviert. In diesem Fall kann der Benutzer nur für kontinuierliche Gruppen mit gültigen Zeichen auswählen.

Beispielsweise können Sie die folgenden MaskedEdit-Steuerelement verwenden, um eine Telefonnummer zu überprüfen:

```cpp
m_wndMaskEdit.EnableMask(
    _T(" ddd  ddd dddd"),  // Mask string
    _T("(___) ___-____"),  // Template string
    _T(' '));              // Default char

m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.

m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt
```

Wenn die Auswahl nach Gruppe aktiviert ist, kann der Benutzer nur die "425", "555" oder "0187" Zeichenfolge Gruppen abrufen. Wenn die Auswahl deaktiviert ist der Benutzer kann den gesamten Text der Telefonnummer abrufen: "(425) 555-0187".

##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly

Gibt an, ob der Text für nur die maskierten Zeichen oder für die gesamte Maske überprüft wird.

```
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] True, um das Validieren der Benutzereingabe für nur Zeichen maskiert. "False", um für die gesamte Maske zu überprüfen. Der Standardwert ist "true".

##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText

Ruft überprüft Text aus dem MaskedEdit-Steuerelement.

```
int GetWindowText(
    LPTSTR lpszStringBuf,
    int nMaxCount) const;

void GetWindowText(CString& rstrString) const;
```

### <a name="parameters"></a>Parameter

*lpszStringBuf*<br/>
[out] Ein Zeiger auf einen Puffer, der den Text von der Edit-Steuerelements empfängt.

*nMaxCount*<br/>
[in] Die maximale Anzahl von Zeichen empfangen.

*rstrString*<br/>
[out] Ein Verweis auf das Zeichenfolgenobjekt, das den Text von der Edit-Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Die erste methodenüberladung gibt die Anzahl der Bytes der Zeichenfolge, die in kopiert wird die *LpszStringBuf* Parameterpuffer; 0, wenn es sich bei der MaskedEdit-Steuerelement keinen Text enthält.

### <a name="remarks"></a>Hinweise

Diese Methode kopiert den Text aus der MaskedEdit-Steuerelement, um die *LpszStringBuf* Puffer oder *RstrString* Zeichenfolge.

Diese Methode definiert [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).

##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar

Wird aufgerufen, durch das Framework, um das angegebene Zeichen mit dem entsprechenden Maskenzeichen zu überprüfen.

```
virtual BOOL IsMaskedChar(
    TCHAR chChar,
    TCHAR chMaskChar) const;
```

### <a name="parameters"></a>Parameter

*chChar*<br/>
[in] Das zu überprüfende Zeichen.

*chMaskChar*<br/>
[in] Das entsprechende Zeichen aus der Maskenzeichenfolge.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die *ChChar* Parameter ist der Typ des von der zugelassenen Zeichen der *ChMaskChar* Parameter ist, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um das Eingabezeichen selbst überprüfen. Weitere Informationen zu Maskenzeichen, finden Sie unter den [CMFCMaskedEdit::EnableMask](#enablemask) Methode.

##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars

Gibt eine Zeichenfolge gültigen Zeichen, die der Benutzer eingeben kann.

```
void SetValidChars(LPCTSTR lpszValid=NULL);
```

### <a name="parameters"></a>Parameter

*lpszValid*<br/>
[in] Eine Zeichenfolge, die den Satz von gültigen Eingabe-Zeichen enthält. NULL bedeutet, dass alle Zeichen gültig sind. Der Standardwert dieses Parameters ist NULL.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um eine Liste der gültigen Zeichen definieren. Wenn ein Eingabezeichen nicht in dieser Liste enthalten ist, wird es nicht vom MaskedEdit-Steuerelement akzeptiert werden.

Im folgenden Codebeispiel wird akzeptiert nur hexadezimale Zahlen.

```cpp
//Mask: 0xFFFF
m_wndMaskEdit.EnableMask(
    _T(" AAAA"),                // The mask string.
    _T("0x____"),               // The literal template string.
    _T('_'));                   // The default character that
                                // replaces the backspace character.
// Valid string characters
m_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));
```

##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText

Sie werden aufgefordert, in der MaskedEdit-Steuerelement.

```
void SetWindowText(LPCTSTR lpszString);
```

### <a name="parameters"></a>Parameter

*lpszString*<br/>
[in] Verweist auf eine auf Null endende Zeichenfolge, die als Eingabeaufforderung verwendet werden.

### <a name="remarks"></a>Hinweise

Diese Methode wird der Text des Steuerelements.

Diese Methode definiert [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)
