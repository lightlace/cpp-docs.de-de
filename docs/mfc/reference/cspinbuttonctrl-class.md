---
title: CSpinButtonCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43b0967309813603e4f683f35c3ca51dce99fd8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374690"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Drehfeld-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Erstellt ein `CSpinButtonCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|Erstellt ein Drehfeld-Steuerelement, und fügt es einer `CSpinButtonCtrl` Objekt.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Erstellt ein Drehfeld-Steuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CSpinButtonCtrl` Objekt.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Acceleration-Informationen für ein Drehfeld-Steuerelement abgerufen.|  
|[CSpinButtonCtrl::GetBase](#getbase)|Ruft den aktuellen Basis für ein Drehfeld-Steuerelement ab.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Ruft einen Zeiger auf das aktuelle Buddyfenster ab.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Ruft die aktuelle Position ein Drehfeld-Steuerelement ab.|  
|[CSpinButtonCtrl::GetRange](#getrange)|Ruft die oberen und unteren Grenzen (Bereich) für ein Drehfeld-Steuerelement ab.|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Legt die Beschleunigung für ein Drehfeld-Steuerelement fest.|  
|[CSpinButtonCtrl::SetBase](#setbase)|Legt die Basis für ein Drehfeld-Steuerelement fest.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Legt das Buddyfenster für ein Drehfeld-Steuerelement fest.|  
|[CSpinButtonCtrl::SetPos](#setpos)|Legt die aktuelle Position für das Steuerelement fest.|  
|[CSpinButtonCtrl:: SetRange](#setrange)|Legt den oberen und unteren Grenzen (Bereich) für ein Drehfeld-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Drehfeldsteuerelement" (auch als auf-ab-Steuerelement bezeichnet) ist ein Paar von Pfeilschaltflächen, die der Benutzer klicken kann, um einen Wert, z. B. eine Bildlaufposition oder eine Zahl, die in einem Steuerelement Companion angezeigt inkrementiert oder dekrementiert. Ein Drehfeld-Steuerelement zugeordnete Wert heißt seiner derzeitigen Position. Ein Drehfeld-Steuerelement wird am häufigsten mit einem Begleit-Steuerelement aufgerufen, als "Buddy-Fenster" verwendet.  
  
 Dieses Steuerelement (und somit die `CSpinButtonCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Suchen Sie für den Benutzer ein Drehfeldsteuerelement häufig seinem Buddyfenster wie ein einzelnes Steuerelement ein. Sie können angeben, dass ein Drehfeld-Steuerelement selbst automatisch neben seinem Buddyfenster positionieren und dieser automatisch die Beschriftung des Fensters Buddy seiner aktuellen Position festgelegt. Sie können ein Drehfeld-Steuerelement mit einem Bearbeitungssteuerelement verwenden, um den Benutzer für numerische Eingabe aufzufordern.  
  
 Klicken auf den Pfeil nach oben bewegt sich die aktuelle Position für die maximale Anzahl und klicken auf den Pfeil nach unten der aktuellen Position in Richtung der Mindestwert. Standardmäßig beträgt 100 und der Höchstwert beträgt 0. Jedes Mal, wenn der niedrigste Wert ist größer als das Maximum festlegen (z. B. wenn die Standardeinstellungen verwendet werden), klicken Sie auf den Stand Pfeil verringert erhöht der Positionswert und klicken Sie auf den Pfeil nach unten.  
  
 Ein Drehfeld-Steuerelement ein Fenster des Buddy fungiert als eine Art vereinfachte Bildlaufleiste angezeigt. Beispielsweise zeigt ein Registerkarten-Steuerelement in einigen Fällen ein Drehfeldsteuerelement, damit der Benutzer zusätzliche Registerkarten Bildlauf anzuzeigende kann.  
  
 Weitere Informationen zur Verwendung von `CSpinButtonCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="create"></a>  CSpinButtonCtrl::Create  
 Erstellt ein Drehfeld-Steuerelement, und fügt es einer `CSpinButtonCtrl` Objekt...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Drehfeldsteuerelement-Stil. Eine beliebige Kombination von Drehfeld-Schaltflächenstile Steuerelement auf das Steuerelement anzuwenden. Diese Formate werden in beschrieben [auf-ab-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb759885) im Windows SDK.  
  
 `rect`  
 Gibt das Drehfeldsteuerelement Größe und Position. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur  
  
 `pParentWnd`  
 Ein Zeiger auf das Drehfeldsteuerelement übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL.**  
  
 `nID`  
 Gibt das Drehfeldsteuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CSpinButtonCtrl` zunächst in zwei Schritten Objekt, rufen Sie den Konstruktor und rufen dann **erstellen**, das das Drehfeld-Steuerelement erstellt, und fügt es der `CSpinButtonCtrl` Objekt.  
  
 Rufen Sie zum Erstellen einer Drehfeld-Steuerelement mit erweiterten Fensterstile [CSpinButtonCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CSpinButtonCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Gibt das Drehfeldsteuerelement-Stil. Eine beliebige Kombination von Drehfeld-Schaltflächenstile Steuerelement auf das Steuerelement anzuwenden. Diese Formate werden in beschrieben [auf-ab-Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb759885) im Windows SDK.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl  
 Erstellt ein `CSpinButtonCtrl`-Objekt.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel  
 Acceleration-Informationen für ein Drehfeld-Steuerelement abgerufen.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nAccel`  
 Anzahl der Elemente im Array vom angegebenen `pAccel`.  
  
 `pAccel`  
 Zeiger auf ein Array von [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) Strukturen, die Beschleunigung-Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Zugriffstaste Strukturen abgerufen.  
  
##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase  
 Ruft den aktuellen Basis für ein Drehfeld-Steuerelement ab.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuellen Preis.  
  
##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy  
 Ruft einen Zeiger auf das aktuelle Buddyfenster ab.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktuelle Buddyfenster.  
  
##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos  
 Ruft die aktuelle Position ein Drehfeld-Steuerelement ab.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpbError*  
 Ein Zeiger auf ein boolescher Wert, der auf NULL, wenn den Wert festgelegt ist, ist erfolgreich abgerufen oder ungleich NULL, wenn ein Fehler auftritt. Wenn dieser Parameter, um festgelegt wird **NULL**, Fehler werden nicht gemeldet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Version gibt die 16-Bit für die aktuelle Position in das niederwertige Wort. Das höherwertige Wort ist ungleich NULL, wenn ein Fehler aufgetreten.  
  
 Die zweite Version gibt die 32-Bit-Position zurück.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Verarbeitung des zurückgegebene Werts aktualisiert das Steuerelement seiner derzeitigen Position basierend auf die Beschriftung des Buddy-Fensters. Das Steuerelement gibt einen Fehler zurück, wenn kein Buddyfenster vorhanden ist oder die Beschriftung einen ungültigen oder außerhalb des gültigen Bereichs Wert angibt.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Ruft die oberen und unteren Grenzen (Bereich) für ein Drehfeld-Steuerelement ab.  
  
```  
DWORD GetRange() const;  
  
void GetRange(
    int& lower,  
    int& upper) const;  
  
void GetRange32(
    int& lower,  
    int &upper) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *Niedrigere*  
 Verweis auf eine ganze Zahl, die die Untergrenze für das Steuerelement empfängt.  
  
 *obere*  
 Verweis auf eine ganze Zahl, die die Obergrenze für das Steuerelement empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Version gibt einen 32-Bit-Wert, der mit den oberen und unteren Grenzen. Das niederwertige Wort ist der obere Grenzwert für das Steuerelement, und das höherwertige Wort ist die untere Grenze.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion `GetRange32` Ruft das Drehfeldsteuerelement Bereich als 32-Bit-Ganzzahl ab.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Legt die Beschleunigung für ein Drehfeld-Steuerelement fest.  
  
```  
BOOL SetAccel(
    int nAccel,  
    UDACCEL* pAccel);
```  
  
### <a name="parameters"></a>Parameter  
 `nAccel`  
 Anzahl der [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) Strukturen gemäß `pAccel`.  
  
 `pAccel`  
 Zeiger auf ein Array von `UDACCEL` -Strukturen, die Beschleunigung Informationen enthalten. Elemente sortiert werden soll, in aufsteigender Reihenfolge auf Grundlage der **nSec** Member.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Legt die Basis für ein Drehfeld-Steuerelement fest.  
  
```  
int SetBase(int nBase);
```  
  
### <a name="parameters"></a>Parameter  
 `nBase`  
 Neue Basiswert für das Steuerelement. Sie können für Dezimalpunkt 10 oder 16 für hexadezimal sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Basiswert im Erfolgsfall, oder 0 (null) ist eine ungültige Basis angegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Basiswert bestimmt, ob Buddy-Fensters Zahlen im dezimalen oder hexadezimalen Ziffern anzeigt. Hexadezimalzahlen sind immer ohne Vorzeichen. Dezimalzahlen werden signiert.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Legt das Buddyfenster für ein Drehfeld-Steuerelement fest.  
  
```  
CWnd* SetBuddy(CWnd* pWndBuddy);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndBuddy`  
 Ein Zeiger auf das neue Buddyfenster.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das vorherige Buddyfenster.  
  
### <a name="remarks"></a>Hinweise  
 Ein Drehfeld-Steuerelement ist fast immer ein anderes Fenster, z. B. ein Bearbeitungssteuerelement, der einige Inhalte anzeigt zugeordnet. Diese anderen Fenster heißt "Kontakt" Drehfeld-Steuerelements.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Legt die aktuelle Position für ein Drehfeld-Steuerelement fest.  
  
```  
int SetPos(int nPos);  
int SetPos32(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Neue Position für das Steuerelement. Dieser Wert muss im Bereich durch den oberen und unteren Grenzen für das Steuerelement angegeben sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Position (16-Bit-Genauigkeit für `SetPos`, 32-Bit-Genauigkeit für `SetPos32`).  
  
### <a name="remarks"></a>Hinweise  
 `SetPos32` die 32-Bit-Position festgelegt.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl:: SetRange  
 Legt den oberen und unteren Grenzen (Bereich) für ein Drehfeld-Steuerelement fest.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Parameter  
 `nLower` und `nUpper`  
 Obere und untere Grenzwerte für das Steuerelement. Für `SetRange`, weder Limit kann größer sein als **UD_MAXVAL** oder kleiner als **UD_MINVAL**; darüber hinaus nicht der Unterschied zwischen beiden Grenzwerte überschreiten **UD_MAXVAL**. `SetRange32` Schränkt die Grenzwerte; Verwenden Sie ganzen Zahlen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion `SetRange32` legt die 32-Bit-Bereich für das Drehfeld-Steuerelement fest.  
  
> [!NOTE]
>  Der Standardbereich für das Drehfeld hat das Maximum auf 0 (null) und das Minimum auf 100 festgelegt. Da der maximale Wert kleiner als der minimale Wert ist, auf den Pfeil nach oben verringert die Position, und klicken auf den Pfeil nach unten, erhöhen sie. Verwendung `CSpinButtonCtrl::SetRange` diese Werte anpassen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl-Klasse](../../mfc/reference/csliderctrl-class.md)
