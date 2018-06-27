---
title: CBitmapButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs:
- C++
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ef1c1a328b785c189a2d7d4a2eb28ec3995a810
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952179"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton-Klasse
Erstellt Pushbutton-Steuerelemente, die mit Bitmapbildern statt mit Text bezeichnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Erstellt ein `CBitmapButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapButton:: AutoLoad](#autoload)|Ordnet eine Schaltfläche in einem Dialogfeld ein Objekt von der `CBitmapButton` -Klasse, lädt die Bitmap(s) anhand des Namens und die Schaltfläche, um die Bitmap passt die Größe.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Initialisiert das Objekt durch eine oder mehrere benannte Bitmapressourcen aus der Ressourcendatei für die Anwendung laden und Anfügen von Bitmaps auf das Objekt an.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|Die Größe der Schaltfläche, um das Bitmuster zu berücksichtigen.|  
  
## <a name="remarks"></a>Hinweise  
 `CBitmapButton` Objekte enthalten, bis zu vier Bitmaps, die Bilder für die verschiedenen Zustände enthalten eine Schaltfläche angenommen: Stand (oder normal) nach unten (oder ausgewählten) mit Fokus, und deaktiviert. Nur die ersten Bitmap ist erforderlich. die anderen sind optional.  
  
 Bitmap-Schaltfläche-Images enthalten die Rahmen um das Bild als auch das Bild selbst. Das Rahmendesign spielt in der Regel in den Status der Schaltfläche an. Beispielsweise ist der Bitmap für den Status der Fokus in der Regel wie die für den Status der Stand jedoch mit einer gestrichelten Rechteck Inset aus den Rahmen oder eine starke durchgezogene Linie an der Grenze. Die Bitmap ähnelt für die deaktivierten, in der Regel Status der für gedrückten Zustand, jedoch niedriger Kontrast (z. B. eine Auswahl Menü abgeblendet oder grau dargestellt enthält).  
  
 Diese Bitmaps kann eine beliebige Größe, jedoch werden alle behandelt, als wären sie die gleiche Größe wie das Bitmuster für gedrückten Zustand.  
  
 "Demand" verschiedene Anwendungen unterschiedliche Kombinationen von Bitmapbildern:  
  
|Nach oben|Nach unten|Focused (Mit Fokus)|Deaktiviert|Application|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||Schaltfläche ohne **WS_TABSTOP** Stil|  
|×|×|×|×|Schaltfläche mit allen Zuständen|  
|×|×|×||Schaltfläche mit **WS_TABSTOP** Stil|  
  
 Legen Sie beim Erstellen einer Bitmap-Schaltflächen-Steuerelement die **BS_OWNERDRAW** Stil, um anzugeben, dass die Schaltfläche Ownerdrawn-ist. Dies bewirkt, dass Windows zum Senden der `WM_MEASUREITEM` und `WM_DRAWITEM` Nachrichten für die Schaltfläche ""; das Framework behandelt diese Nachrichten und die Darstellung der Schaltfläche für Sie verwaltet.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>So erstellen ein Bitmap-Schaltflächen-Steuerelement im Clientbereich eines Fensters  
  
1.  Erstellen Sie ein bis vier Bitmapbildern für die Schaltfläche.  
  
2.  Erstellen der [CBitmapButton](#cbitmapbutton) Objekt.  
  
3.  Rufen Sie die [erstellen](../../mfc/reference/cbutton-class.md#create) Funktion erstellen das Windows-Schaltflächensteuerelement und fügen Sie es auf die `CBitmapButton` Objekt.  
  
4.  Rufen Sie die [LoadBitmaps](#loadbitmaps) Memberfunktion versucht, die mithilfe einer Bitmapressourcen geladen werden, nachdem die Schaltfläche "Bitmap" erstellt wurde.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Ein Bitmap-Schaltflächen-Steuerelement in einem Dialogfeld einschließen  
  
1.  Erstellen Sie ein bis vier Bitmapbildern für die Schaltfläche.  
  
2.  Erstellen einer Dialogfeldvorlage Ownerdrawn-Schaltfläche positioniert werden soll die Schaltfläche "Bitmap". Die Größe der Schaltfläche in der Vorlage spielt keine Rolle.  
  
3.  Die Beschriftung der Schaltfläche auf einen Wert festgelegt wie z. B. " **MYIMAGE**" und definieren Sie z. B. ein Symbol für die Schaltfläche **IDC_MYIMAGE**.  
  
4.  In Ihrer Anwendung Ressourcenskript geben jedes der Bilder für die Schaltfläche erstellt eine ID erstellt, die durch Anhängen eines den Buchstaben "U", "D", "F", oder "X" (nach oben, unten, mit Fokus und deaktiviert) auf die Zeichenfolge für die Beschriftung der Schaltfläche in Schritt 3. Für die Beschriftung der Schaltfläche " **MYIMAGE**," die IDs wäre z. B. " **MYIMAGEU**," " **MYIMAGED**," " **MYIMAGEF**," und " **MYIMAGEX**. " Sie **müssen** geben die ID der Ihre Bitmaps in doppelten Anführungszeichen. Andernfalls der Ressourcen-Editor weist eine ganze Zahl auf die Ressource und MFC schlagen fehl, wenn das Bild zu laden.  
  
5.  In Dialogklasse Ihrer Anwendung (abgeleitet `CDialog`), Hinzufügen einer `CBitmapButton` Member-Objekt.  
  
6.  In der `CDialog` des Objekts [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) Aufruf der Routine, die `CBitmapButton` des Objekts [AutoLoad](#autoload) Funktion als Parameter Kontroll-ID für die Schaltfläche mit und die `CDialog` Objekt **dies** Zeiger.  
  
 Wenn Sie Windows-benachrichtigungsmeldungen, z. B. BN_CLICKED, behandeln möchten von ein Bitmap-Schaltflächen-Steuerelement zu seinem übergeordneten Element gesendet (in der Regel eine abgeleitete Klasse `CDialog`), zum Hinzufügen der `CDialog`-abgeleitete Objekt ein meldungszuordnung Eintrag und Meldungshandler Element die Funktion für jede Nachricht. Die Benachrichtigungen gesendet werden, indem eine `CBitmapButton` Objekt sind identisch mit denen per eine [CButton](../../mfc/reference/cbutton-class.md) Objekt.  
  
 Die Klasse [CToolBar](../../mfc/reference/ctoolbar-class.md) benötigt einen anderen Ansatz für ein Bitmapschaltflächen.  
  
 Weitere Informationen zu `CBitmapButton`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="autoload"></a>  CBitmapButton:: AutoLoad  
 Ordnet eine Schaltfläche in einem Dialogfeld ein Objekt von der `CBitmapButton` -Klasse, lädt die Bitmap(s) anhand des Namens und die Schaltfläche, um die Bitmap passt die Größe.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Die Schaltfläche Steuerelement-ID.  
  
 *pParent*  
 Ein Zeiger auf das Objekt, das die Schaltfläche "" besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `AutoLoad` Funktion, um eine Ownerdrawn-Schaltfläche in einem Dialogfeld als Bitmapschaltfläche zu initialisieren. Anweisungen für die Verwendung dieser Funktion finden Sie in den Hinweisen für die `CBitmapButton` Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton  
 Erstellt ein `CBitmapButton`-Objekt.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen der C++ `CBitmapButton` -Objekt, rufen Sie [CButton::Create](../../mfc/reference/cbutton-class.md#create) erstellen das Windows-Schaltflächensteuerelement und fügen Sie es auf die `CBitmapButton` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps  
 Verwenden Sie diese Funktion beim Laden von Bitmapbildern identifiziert ihre Ressourcennamen oder ID-Nummern, oder wenn Sie nicht verwenden können sollen die `AutoLoad` ausgeführt, da z. B. erstellen eine Bitmapschaltfläche, die nicht Teil eines Dialogfelds ist.  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszBitmapResource*  
 Verweist auf die Null-terminierte Zeichenfolge, die den Namen der Bitmap für eine Bitmapschaltfläche Normal oder "fehlerfrei" enthält. Erforderlich.  
  
 *lpszBitmapResourceSel*  
 Verweist auf die Null-terminierte Zeichenfolge mit dem Namen der Bitmap für eine Schaltfläche "Bitmap" ausgewählt, der oder "inaktiv". Möglicherweise **NULL**.  
  
 *lpszBitmapResourceFocus*  
 Verweist auf die Null-terminierte Zeichenfolge mit dem Namen der Bitmap für einer Bitmapschaltfläche mit Fokus Zustand. Möglicherweise **NULL**.  
  
 *lpszBitmapResourceDisabled*  
 Verweist auf die Null-terminierte Zeichenfolge mit dem Namen der Bitmap für eine Bitmapschaltfläche deaktiviert. Möglicherweise **NULL**.  
  
 *nIDBitmapResource*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource für eine Bitmapschaltfläche Normal oder "fehlerfrei" an. Erforderlich.  
  
 *nIDBitmapResourceSel*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource an, für eine Schaltfläche "Bitmap" ausgewählt, der oder "inaktiv". 0 kann sein.  
  
 *nIDBitmapResourceFocus*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource für eine Bitmapschaltfläche mit Fokus Status an. 0 kann sein.  
  
 *nIDBitmapResourceDisabled*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource für eine Bitmapschaltfläche deaktiviert. 0 kann sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent  
 Mit dieser Funktion wird zum Ändern der Größe einer Bitmapschaltfläche, um die Größe der Bitmap.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

