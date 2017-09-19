---
title: CBitmapButton Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- buttons, bitmap
- CBitmapButton class
- bitmaps, button controls
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 16d39cb380b75e6dcef71dda01626f120d5c12fb
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmapbutton-class"></a>CBitmapButton-Klasse
Erstellt Pushbutton-Steuerelemente, die mit Bitmapbildern statt mit Text bezeichnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|Erstellt ein `CBitmapButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapButton:: AutoLoad](#autoload)|Ordnet eine Schaltfläche in einem Dialogfeld mit einem Objekt der `CBitmapButton` -Klasse lädt die Bitmap(s) nach Namen und passt die Größe der Schaltfläche, um die Bitmap anpassen.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|Initialisiert das Objekt durch eine oder mehrere benannte Bitmapressourcen von Ressourcendatei der Anwendung geladen und die Bitmaps für das Objekt anfügen.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|Die Größe der Schaltfläche, um die Bitmap zu berücksichtigen.|  
  
## <a name="remarks"></a>Hinweise  
 `CBitmapButton`Objekte enthalten, bis zu vier Bitmaps, die Bilder für die verschiedenen Zustände enthalten eine Schaltfläche kann davon ausgehen: oben (oder normal) nach unten (oder ausgewählten) mit Fokus, und deaktiviert. Nur die ersten Bitmap ist erforderlich. die anderen sind optional.  
  
 Bitmap-Bilder enthalten den Rahmen um das Bild als auch das Bild selbst. Der Rahmen spielt in der Regel eine mit dem Status der Schaltfläche. Beispielsweise ist die Bitmap für den Status der Fokus in der Regel wie für gedrückten Zustand jedoch mit einer gestrichelten Rechteck Inset aus den Rahmen oder eine dicke durchgehende Linie an der Grenze. Die Bitmap ähnelt für die deaktivierten, in der Regel Zustand der gedrückten Zustand jedoch niedriger Kontrast (z. B. eine Auswahl im Menü deaktiviert oder abgeblendet) ist.  
  
 Diese Bitmaps können von beliebiger Größe sein, aber alle werden behandelt, als handele es sich um die gleiche Größe wie die Bitmap für gedrückten Zustand.  
  
 Verschiedene Anwendungen erfordern verschiedene Kombinationen von Bitmap-Bildern:  
  
|Nach oben|Nach unten|Focused (Mit Fokus)|Deaktiviert|Anwendung|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||Schaltfläche ohne **WS_TABSTOP** Stil|  
|×|×|×|×|Schaltfläche mit allen Zuständen|  
|×|×|×||Schaltfläche mit **WS_TABSTOP** Stil|  
  
 Legen Sie beim Erstellen einer Bitmap-Schaltflächen-Steuerelement die **BS_OWNERDRAW** zu geben, dass die Schaltfläche Ownerdrawn-Stil. Dies bewirkt, dass Windows zum Senden der `WM_MEASUREITEM` und `WM_DRAWITEM` Nachrichten für die Schaltfläche; das Framework diese Nachrichten verarbeitet und die Darstellung der Schaltfläche für Sie verwaltet.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>Erstellen Sie ein Bitmap-Schaltflächen-Steuerelement im Clientbereich eines Fensters  
  
1.  Erstellen Sie ein bis vier Bitmaps für die Schaltfläche.  
  
2.  Erstellen der [CBitmapButton](#cbitmapbutton) Objekt.  
  
3.  Rufen Sie die [erstellen](../../mfc/reference/cbutton-class.md#create) Funktion das Schaltflächen-Steuerelement von Windows zu erstellen und diese an die `CBitmapButton` Objekt.  
  
4.  Rufen Sie die [LoadBitmaps](#loadbitmaps) Memberfunktion die Bitmapressourcen laden, nach dem Erstellen die Bitmapschaltfläche.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>Ein Bitmap-Schaltflächen-Steuerelement in einem Dialogfeld einschließen  
  
1.  Erstellen Sie ein bis vier Bitmaps für die Schaltfläche.  
  
2.  Erstellen einer Dialogfeldvorlage Ownerdrawn-Schaltfläche positioniert, in dem die Bitmapschaltfläche angezeigt werden soll. Die Größe der Schaltfläche in der Vorlage spielt keine Rolle.  
  
3.  Legen Sie die Beschriftung der Schaltfläche auf einen Wert wie " **MYIMAGE**" und definieren Sie ein Symbol für die Schaltfläche wie z. B. **IDC_MYIMAGE**.  
  
4.  In Ihrer Anwendung Ressourcenskript geben jedes der Bilder für die Schaltfläche erstellt eine ID erstellt, die durch Anhängen einer der Buchstaben "U", "D", "F", oder "X" (nach oben, unten, konzentriert und deaktiviert) auf die Zeichenfolge für die Beschriftung der Schaltfläche in Schritt 3. Für die Beschriftung der Schaltfläche " **MYIMAGE**," die IDs wäre z. B. " **MYIMAGEU**," " **MYIMAGED**," " **MYIMAGEF**," und " **MYIMAGEX**." Sie **müssen** Geben Sie die ID für die Bitmap in doppelte Anführungszeichen gesetzt. Andernfalls der Ressourcen-Editor weist eine ganze Zahl für die Ressource und MFC schlägt fehl, wenn das Bild geladen.  
  
5.  In Ihrer Anwendung Dialogfeldklasse (abgeleitet `CDialog`), Hinzufügen einer `CBitmapButton` Member-Objekt.  
  
6.  In der `CDialog` des Objekts [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) routinemäßig ausgeführt werden, rufen die `CBitmapButton` des Objekts [AutoLoad](#autoload) funktioniert, verwenden als Parameter für die Schaltfläche Steuerelement-ID und die `CDialog` des Objekts **dies** Zeiger.  
  
 Wenn Sie Windows-Benachrichtigungen, wie z. B. behandeln möchten **BN_CLICKED**und wurde durch ein Bitmap-Schaltflächen-Steuerelement zu seinem übergeordneten Element (i. d. r. eine abgeleitete Klasse **CDialog)**, Hinzufügen der `CDialog`-abgeleitete Objekt einer meldungszuordnung Eintrag und Meldungshandler Memberfunktion für jede Nachricht. Die Benachrichtigungen gesendet werden, indem eine `CBitmapButton` Objekt sind identisch mit denen per ein [CButton](../../mfc/reference/cbutton-class.md) Objekt.  
  
 Die Klasse [CToolBar](../../mfc/reference/ctoolbar-class.md) bietet einen anderen Ansatz für Schaltflächen.  
  
 Weitere Informationen zu `CBitmapButton`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="autoload"></a>CBitmapButton:: AutoLoad  
 Ordnet eine Schaltfläche in einem Dialogfeld mit einem Objekt der `CBitmapButton` -Klasse lädt die Bitmap(s) nach Namen und passt die Größe der Schaltfläche, um die Bitmap anpassen.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Die Schaltfläche Steuerelement-ID  
  
 `pParent`  
 Ein Zeiger auf das Objekt, das die Schaltfläche besitzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `AutoLoad` Funktion eine Ownerdrawn-Schaltfläche in einem Dialogfeld als eine Bitmapschaltfläche initialisiert werden. Informationen zur Verwendung dieser Funktion sind in den Hinweisen für die `CBitmapButton` Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#75;](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton  
 Erstellt ein `CBitmapButton`-Objekt.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen der C++ `CBitmapButton` -Objekt, rufen Sie [CButton::Create](../../mfc/reference/cbutton-class.md#create) das Schaltflächen-Steuerelement von Windows zu erstellen und diese an die `CBitmapButton` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#57;](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps  
 Wenn Sie laden Bitmapbilder identifiziert, deren Namen oder die ID-Nummern, oder wenn Sie nicht verwenden möchten, verwenden Sie diese Funktion der `AutoLoad` Funktion, da z. B. eine Bitmapschaltfläche erstellen, die nicht Teil eines Dialogfelds.  
  
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
 Verweist auf die auf Null endende Zeichenfolge, die den Namen der Bitmap für eine Bitmapschaltfläche Normal oder "Status up" enthält. Erforderlich.  
  
 *lpszBitmapResourceSel*  
 Punkte, die Null-terminierte Zeichenfolge mit dem Namen der Bitmap eine Bitmapschaltfläche aktiviert die oder "inaktiv". Möglicherweise **NULL**.  
  
 *lpszBitmapResourceFocus*  
 Verweist auf die auf Null endende Zeichenfolge, die den Namen der Bitmap für einer Bitmapschaltfläche enthält hauptsächlich Zustand. Möglicherweise **NULL**.  
  
 *lpszBitmapResourceDisabled*  
 Verweist auf die auf Null endende Zeichenfolge, die den Namen der Bitmap für eine Bitmapschaltfläche deaktivierten Zustand enthält. Möglicherweise **NULL**.  
  
 *nIDBitmapResource*  
 Gibt die Ressourcen-ID der Bitmapressource für eine Bitmapschaltfläche Normal oder "Status up". Erforderlich.  
  
 *nIDBitmapResourceSel*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource an, für eine Bitmapschaltfläche ausgewählte des oder "inaktiv". 0 kann sein.  
  
 *nIDBitmapResourceFocus*  
 Gibt die Ressourcen-ID-Nummer der Bitmapressource für eine Bitmapschaltfläche focused-Zustand. 0 kann sein.  
  
 *nIDBitmapResourceDisabled*  
 Gibt die Ressourcen-ID der Bitmapressource für eine Bitmapschaltfläche deaktivierten Zustand. 0 kann sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#58;](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>CBitmapButton::SizeToContent  
 Rufen Sie diese Funktion, um eine Bitmapschaltfläche, um die Größe der Bitmap für die Größe zu ändern.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#59;](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


