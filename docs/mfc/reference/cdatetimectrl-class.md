---
title: CDateTimeCtrl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
dev_langs:
- C++
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3359b506217d2828207e06341fbf1fe53b3c0719
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl-Klasse
Kapselt die Funktionalität eines Steuerelements für die Datums- und Zeitauswahl.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Erstellt ein `CDateTimeCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Schließt das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement.|  
|[CDateTimeCtrl::Create](#create)|Die Datums- / Zeitauswahl-Steuerelement erstellt, und fügt es der `CDateTimeCtrl` Objekt.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Ruft Informationen über das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement ab.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Gibt die ideale Größe der Datums- und Uhrzeitangabe Kontoauswahl-Steuerelement, das erforderlich sind, um die aktuellen Datums- oder Zeitangabe anzuzeigen.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Ruft die Farbe für einen bestimmten Teil der Monatskalender innerhalb der Datums- / Zeitauswahl-Steuerelement ab.|  
|[CDateTimeCtrl:: GetMonthCalCtrl](#getmonthcalctrl)|Ruft die `CMonthCalCtrl` Objekt mit der Datums- / Zeitauswahl-Steuerelement zugewiesen ist.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Ruft die derzeit von das Datum und Uhrzeit-Auswahlsteuerelement untergeordneten Monatskalender-Steuerelement verwendete Schriftart ab.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Ruft den Stil des aktuellen Datums- / Zeitauswahl-Steuerelements ab.|  
|[CDateTimeCtrl::GetRange](#getrange)|Ruft die aktuellen minimalen und maximalen zulässig Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement.|  
|[CDateTimeCtrl::GetTime](#gettime)|Ruft die aktuell ausgewählten Uhrzeit über ein Datum und Uhrzeit Kontoauswahl-Steuerelement ab und fügt sie in einem angegebenen `SYSTEMTIME` Struktur.|  
|[CDateTimeCtrl:: setFormat initialisiert](#setformat)|Legt die Anzeige eines Steuerelements in Übereinstimmung mit einer angegebenen Formatzeichenfolge für Datums- und Zeitauswahl.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Legt die Farbe für einen bestimmten Teil der Monatskalender in einem Datums- und Zeitauswahl-Steuerelement fest.|  
|[CDateTimeCtrl:: SetMonthCalFont](#setmonthcalfont)|Legt die Schriftart, die die Datums- / Zeitauswahl-Steuerelements untergeordneten Monatskalender-Steuerelement verwenden.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Legt den Stil des aktuellen Datums- / Zeitauswahl-Steuerelements fest.|  
|[CDateTimeCtrl::SetRange](#setrange)|Legt die minimalen und maximalen zulässigen Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement fest.|  
|[CDateTimeCtrl::SetTime](#settime)|Legt die Zeit in einem Datums- und Zeitauswahl-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Das Datum und Uhrzeit die Datumsauswahl (DTP-Steuerelement) bietet eine einfache Schnittstelle zum Austauschen von Informationen über Zugriffsdatum und-Zeitpunkt mit einem Benutzer. Diese Schnittstelle enthält Felder, von die jede einen Teil der Datums- und Uhrzeitangabe Informationen gespeichert, die im Steuerelement angezeigt. Der Benutzer kann den Informationen in das Steuerelement durch Ändern des Inhalts der Zeichenfolge in einem bestimmten Feld ändern. Der Benutzer kann von einem Feld mit der Maus oder Tastatur navigieren.  
  
 Sie können die Datums- / Zeitauswahl-Steuerelement anpassen, indem Sie eine Vielzahl von Formaten auf das Objekt angewendet werden, bei der Erstellung. Finden Sie unter [Datums- und Uhrzeitformate Zeitauswahl-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb761728) in das Windows SDK für Weitere Informationen zu Stilen, die speziell für das Datums- / Zeitauswahl-Steuerelement. Sie können das Anzeigeformat des Steuerelements DTP mit Datenformate festlegen. Diese Stile Format werden im Windows SDK-Thema unter "Format-Formatvorlagen" beschrieben [Datums- und Uhrzeitformate Zeitauswahl-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 Die Datums- / Zeitauswahl-Steuerelement außerdem Benachrichtigungen und Rückrufe, die in beschriebenen verwendet [Verwenden von CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 Erstellt ein `CDateTimeCtrl`-Objekt.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 Schließt das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird schließt die Dropdownkalender für das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>CDateTimeCtrl::Create  
 Die Datums- / Zeitauswahl-Steuerelement erstellt, und fügt es der `CDateTimeCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Kombination aus Datum-Zeit-Steuerelementtypen an. Finden Sie unter [Datums- und Uhrzeitformate Zeitauswahl-Steuerelement](http://msdn.microsoft.com/library/windows/desktop/bb761728) in das Windows SDK für Weitere Informationen zu Datums- und Zeitauswahl Zeitformaten.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Position und Größe der Datums- / Zeitauswahl-Steuerelement ist.  
  
 `pParentWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das das übergeordnete Fenster eines Datums- / Zeitauswahl-Steuerelement darstellt. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, die Datums- / Zeitauswahl-Steuerelements Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Erstellung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>So erstellen ein Datum und Uhrzeit die Datumsauswahl  
  
1.  Rufen Sie [CDateTimeCtrl](#cdatetimectrl) zum Erstellen einer `CDateTimeCtrl` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die die Windows Datums- und Zeitauswahl erstellt und fügt es der `CDateTimeCtrl` Objekt.  
  
 Beim Aufruf **erstellen**, die allgemeine Steuerelemente werden initialisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 Ruft Informationen über das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement ab.  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pDateTimePickerInfo`|Ein Zeiger auf eine [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729) -Struktur, die eine Beschreibung des aktuellen Datums- / Zeitauswahl-Steuerelements empfängt.<br /><br /> Der Aufrufer ist verantwortlich für die Zuordnung von dieser Struktur. Diese Methode jedoch initialisiert die `cbSize` Member der Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel gibt an, ob Informationen über das aktuelle Datum und Uhrzeit die Datumsauswahl erfolgreich abgerufen.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 Ruft die Farbe für einen bestimmten Teil der Monatskalender innerhalb der Datums- / Zeitauswahl-Steuerelement ab.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `iColor`  
 Ein `int` Wert, der die Farbbereich des abzurufenden Monatskalender angibt. Eine Liste von Werten, finden Sie unter der `iColor` -Parameter für [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die Farbe-Einstellung für den angegebenen Teil der Monatskalender-Steuerelement im Erfolgsfall darstellt. Die Funktion gibt-1 zurück, wenn Fehler auftreten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>CDateTimeCtrl:: GetMonthCalCtrl  
 Ruft die `CMonthCalCtrl` Objekt mit der Datums- / Zeitauswahl-Steuerelement zugewiesen ist.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) -Objekt, oder **NULL** oder wenn Fehler auftreten, wenn das Fenster nicht sichtbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Datums- und Zeitauswahlsteuerelemente erstellen ein Monatskalender-Steuerelement untergeordnete, klickt der Benutzer den Dropdown Pfeil. Wenn die `CMonthCalCtrl` Objekt nicht mehr erforderlich ist, werden sie zerstört wird, weshalb die Anwendung muss nicht zum Speichern von das Objekt, das Datums-/ Zeitauswahl-Steuerelement des untergeordneten Monatskalender darstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 Ruft die derzeit von das Datum und Uhrzeit-Auswahlsteuerelement Monatskalender-Steuerelement verwendete Schriftart ab.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) -Objekt, oder **NULL** Wenn Fehler auftreten.  
  
### <a name="remarks"></a>Hinweise  
 Die `CFont` Objekt verweist, zu der Rückgabewert ist ein temporäres Objekt und während der nächsten Verarbeitung Leerlaufzeit zerstört wird.  
  
##  <a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 Ruft den Stil des im Dropdown-Monatskalender-Steuerelement, das das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement zugeordnet ist.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Art der Dropdown-Monatskalender-Steuerelement, das eine bitweise Kombination ist (oder) der Datums- und Zeitauswahl-Steuerelementtypen. Weitere Informationen finden Sie unter [Steuerelementtypen für die Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getrange"></a>CDateTimeCtrl::GetRange  
 Ruft die aktuellen minimalen und maximalen zulässig Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pMinRange`  
 Ein Zeiger auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, das das früheste zulässige enthält die `CDateTimeCtrl` Objekt.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` Objekt oder eine `CTime` Objekt, das die späteste Uhrzeit, die in zulässigen enthält die `CDateTimeCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der enthält Flags, die angeben, welche Bereiche festgelegt werden. If  
  
 `return value & GDTR_MAX` == 0  
  
 der zweite Parameter gültig ist. Auf ähnliche Weise, wenn  
  
 `return value & GDTR_MIN` == 0  
  
 der erste Parameter gültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767)gemäß der Beschreibung im Windows SDK. In MFC Implementierung, geben Sie `COleDateTime` oder `CTime` Verwendungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>CDateTimeCtrl::GetTime  
 Ruft die aktuell ausgewählten Uhrzeit über ein Datum und Uhrzeit Kontoauswahl-Steuerelement ab und fügt sie in einem angegebenen `SYSTEMTIME` Struktur.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *timeDest*  
 In der ersten Version, die einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhält. In der zweiten Version, die einen Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhält.  
  
 *pTimeDest*  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Darf nicht sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Version, die ungleich NULL, wenn die Zeit in erfolgreich geschrieben werden die `COleDateTime` -Objekt, andernfalls 0. In der zweiten und dritten Version können eine `DWORD` Wert gleich dem **DwFlag** Elementgruppe der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Struktur. Finden Sie unter der **"Hinweise"** weiter unten im Abschnitt Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769)gemäß der Beschreibung im Windows SDK. In der MFC-Implementierung von **GetTime**, können Sie `COleDateTime` oder `CTime` Klassen, oder Sie können eine `SYSTEMTIME` -Struktur, um die Informationen zu speichern.  
  
 Der Rückgabewert `DWORD` in der zweiten und dritten Version können höher gibt an, und zwar unabhängig davon, ob die Datums- / Zeitauswahl-Steuerelement auf den Status "kein Datum" festgelegt ist wie angegeben in der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Strukturmember `dwFlags`. Wenn der Rückgabewert gleich **GDT_NONE**, das Steuerelement den Status "kein Datum" festgelegt ist, und verwendet die **DTS_SHOWNONE** Stil. Wenn der Rückgabewert gleich **GDT_VALID**, die Systemzeit ist am Zielspeicherort erfolgreich gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 Gibt die ideale Größe der Datums- und Uhrzeitangabe Kontoauswahl-Steuerelement, das erforderlich sind, um die aktuellen Datums- oder Zeitangabe anzuzeigen.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `psize`|Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) Struktur, die die ideale Größe für das Steuerelement enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist immer `true`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft die ideale Größe zum Anzeigen von Datums- / Zeitauswahl-Steuerelement ab.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>CDateTimeCtrl:: setFormat initialisiert  
 Legt die Anzeige eines Steuerelements in Übereinstimmung mit einer angegebenen Formatzeichenfolge für Datums- und Zeitauswahl.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrFormat*  
 Ein Zeiger auf eine Formatzeichenfolge mit 0 (null) beendet, die den gewünschten Anzeige definiert. Wenn dieser Parameter auf **NULL** wird das Steuerelement auf die Standardformat-Zeichenfolge für das aktuelle Format zurückgesetzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
> [!NOTE]
>  Erfolg oder Fehler für diesen Aufruf ist eine Benutzereingabe nicht ermittelt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 Legt die Farbe für einen bestimmten Teil der Monatskalender in einem Datums- und Zeitauswahl-Steuerelement fest.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Parameter  
 `iColor`  
 `int`-Wert, welcher Bereich der im Monatskalender-Steuerelement festlegen. Dieser Wert kann eine der folgenden Werte sein.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|MCSC_BACKGROUND|Legen Sie die Farbe des Hintergrunds zwischen Monaten angezeigt.|  
|MCSC_MONTHBK|Legen Sie die Farbe des Hintergrunds in einem Monat angezeigt.|  
|MCSC_TEXT|Legen Sie die Farbe, die zum Anzeigen von Text in einem Monat verwendet.|  
|MCSC_TITLEBK|Legen Sie die Farbe des Hintergrunds im Titel des Kalenders angezeigt.|  
|MCSC_TITLETEXT|Legen Sie die Farbe, die zum Anzeigen von Text innerhalb des Kalenders Titel verwendet.|  
|MCSC_TRAILINGTEXT|Legen Sie die Farbe, die zum Anzeigen von Kopf- und nachfolgende Tag Text verwendet. Kopf- und die nachfolgenden Tage sind die Tage von der vorherigen und folgenden Monate, die auf dem aktuellen Kalender angezeigt werden.|  
  
 `ref`  
 Ein **COLORREF** Wert, der die Farbe, die für den angegebenen Bereich eines Monatskalender festgelegt werden darstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die vorherige Einstellung der Farbe für den angegebenen Teil der Monatskalender-Steuerelement im Erfolgsfall darstellt. Die Nachricht zurückgegeben, andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="setmonthcalfont"></a>CDateTimeCtrl:: SetMonthCalFont  
 Legt die Schriftart, die die Datums- / Zeitauswahl-Steuerelements untergeordneten Monatskalender-Steuerelement verwenden.  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hFont`  
 Handle für die Schriftart, die festgelegt werden.  
  
 `bRedraw`  
 Gibt an, ob das Steuerelement sofort neu sollten beim Festlegen der Schrift gezeichnet werden. Wenn dieser Parameter auf **"true"** bewirkt, dass das Steuerelement selbst neu zeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Wenn Sie diesen Code verwenden, sollten Sie ein Mitglied, Ihre `CDialog`-abgeleitete Klasse mit dem Namen `m_MonthFont` des Typs **CFont**.  
  
##  <a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 Legt den Stil des im Dropdown-Monatskalender-Steuerelement, das das aktuelle Datum und Uhrzeit Zeitauswahl-Steuerelement zugeordnet ist.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwStyle`|Einem neuen Monat "Kalender" Steuerelementformats, die eine bitweise Kombination (OR) von Month Calendar-Steuerelementtypen ist. Weitere Informationen finden Sie unter [Steuerelementtypen für die Calendar Month](http://msdn.microsoft.com/library/windows/desktop/bb760919).|  
  
### <a name="return-value"></a>Rückgabewert  
 Das frühere Format des im Dropdown-Monatskalender-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`, d. h. verwendet, um die Datums- / Zeitauswahl-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel legt fest, der Datum und Uhrzeit die Datumsauswahl Wochennummern, abgekürzten Namen der Tage der Woche und kein heute Indikator angezeigt.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CDateTimeCtrl::SetRange  
 Legt die minimalen und maximalen zulässigen Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement fest.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>Parameter  
 `pMinRange`  
 Ein Zeiger auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, das das früheste zulässige enthält die `CDateTimeCtrl` Objekt.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` Objekt oder eine `CTime` Objekt, das die späteste Uhrzeit, die in zulässigen enthält die `CDateTimeCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780)gemäß der Beschreibung im Windows SDK. In MFC Implementierung, geben Sie `COleDateTime` oder `CTime` Verwendungen. Wenn die `COleDateTime` Objekt verfügt über eine **NULL** Status, der Bereich entfernt werden. Wenn die `CTime` Zeiger oder `COleDateTime` Zeiger **NULL**, Bereich entfernt werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="settime"></a>CDateTimeCtrl::SetTime  
 Legt die Zeit in einem Datums- und Zeitauswahl-Steuerelement fest.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *timeNew*  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt mit der auf dem das Steuerelement festgelegt wird.  
  
 *pTimeNew*  
 In der zweiten Version über einen Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, enthält die Zeit, zu dem das Steuerelement festgelegt werden. In der dritten Version über einen Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, enthält die Zeit, zu dem das Steuerelement festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782)gemäß der Beschreibung im Windows SDK. In der MFC-Implementierung von **SetTime**, können Sie die `COleDateTime` oder `CTime` Klassen, oder Sie können eine `SYSTEMTIME` -Struktur, die Zeitinformationen festlegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl-Klasse](../../mfc/reference/cmonthcalctrl-class.md)
