---
title: CDateTimeCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], CDateTimeCtrl class
- date-picking functionality
- CDateTimeCtrl class
- DateTimePicker control [MFC]
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
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
ms.openlocfilehash: e5407934021abdb64dfb625e3dfb2c1841b7a5f0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl-Klasse
Kapselt die Funktionalität eines Steuerelements für die Datums- und Zeitauswahl.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|Erstellt ein `CDateTimeCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|Schließt das aktuelle Datums- / Zeitauswahl-Steuerelement.|  
|[CDateTimeCtrl::Create](#create)|Die Datums- / Zeitauswahl-Steuerelement erstellt, und fügt es der `CDateTimeCtrl` Objekt.|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|Ruft Informationen über die aktuellen Datums- / Zeitauswahl.|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|Gibt die ideale Größe der Datums- / Zeitauswahl, die erforderlich sind, um das aktuelle Datum oder die Uhrzeit anzuzeigen.|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|Ruft die Farbe für einen bestimmten Teil des Monatskalender innerhalb der Datums- / Zeitauswahl-Steuerelement ab.|  
|[CDateTimeCtrl:: GetMonthCalCtrl](#getmonthcalctrl)|Ruft die `CMonthCalCtrl` die Datums- / Zeitauswahl-Steuerelement zugeordnete Objekt.|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|Ruft die derzeit von der Datums- und / Zeitauswahl-Steuerelement untergeordnete Monatskalender-Steuerelement verwendete Schriftart ab.|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|Ruft den Stil des aktuellen Datums- / Zeitauswahl-Steuerelements ab.|  
|[CDateTimeCtrl::GetRange](#getrange)|Ruft die aktuellen Minimal- und Maximalwerte Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement zulässig.|  
|[CDateTimeCtrl::GetTime](#gettime)|Ruft die derzeit ausgewählten Uhrzeit aus einem Datums- / Zeitauswahl-Steuerelement ab und fügt es in einem angegebenen `SYSTEMTIME` Struktur.|  
|[CDateTimeCtrl:: setFormat initialisiert](#setformat)|Legt die Anzeige eines Steuerelements in Übereinstimmung mit einer angegebenen Formatzeichenfolge für Datums- und Zeitauswahl.|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|Legt die Farbe für einen bestimmten Teil des Monatskalender in einem Datums- / Zeitauswahl-Steuerelement fest.|  
|[CDateTimeCtrl:: SetMonthCalFont](#setmonthcalfont)|Legt die Schriftart, die die Datums- / Zeitauswahl-Steuerelements untergeordneten Monatskalender-Steuerelement verwenden.|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|Legt den Stil des aktuellen Datums- / Zeitauswahl-Steuerelements.|  
|[CDateTimeCtrl::SetRange](#setrange)|Legt die minimale und maximale zulässige Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement fest.|  
|[CDateTimeCtrl::SetTime](#settime)|Legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Das Datum und Zeitauswahl (DTP-Steuerelement) bietet eine einfache Schnittstelle zum Austauschen von Informationen über Datum und Uhrzeit mit einem Benutzer. Diese Schnittstelle enthält Felder, von die jede einen Teil der Datum und Uhrzeit-Informationen gespeichert, die im Steuerelement angezeigt. Der Benutzer kann den Informationen in das Steuerelement durch Ändern des Inhalts der Zeichenfolge in ein bestimmtes Feld ändern. Der Benutzer kann von einem Feld mit der Maus oder der Tastatur verschieben.  
  
 Sie können die Datums- und Zeitauswahl anpassen, indem Sie beim Erstellen eine Vielzahl von Stilen auf das Objekt angewendet. Finden Sie unter [Datum und Zeit Datumsauswahl Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb761728) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zu Stilen, die spezifisch für die Datums- / Zeitauswahl-Steuerelement. Sie können das Anzeigeformat des Format-Stilen DTP-Steuerelements festlegen. Diese Stile Format werden unter "Format Formatvorlagen" beschrieben, der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)] Thema [Datum und Zeit Datumsauswahl Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb761728).  
  
 Die Datums- und Zeitauswahl außerdem Benachrichtigungen und Rückrufe, die in beschriebenen verwendet [Verwenden von CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdtctl.h  
  
##  <a name="a-namecdatetimectrla--cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 Erstellt ein `CDateTimeCtrl`-Objekt.  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="a-nameclosemonthcala--cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 Schließt das aktuelle Datums- / Zeitauswahl-Steuerelement.  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`besteht, wird verwendet, um programmgesteuert auf das Steuerelement für die Datums- / Zeitauswahl zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Dropdown-Kalender für das aktuelle Datums- / Zeitauswahl-Steuerelement geschlossen.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1&5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="a-namecreatea--cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::Create  
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
 Gibt die Kombination aus Datum-Uhrzeit-Steuerelementtypen. Finden Sie unter [Datum und Zeit Datumsauswahl Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb761728) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zu Datums- und Zeitauswahl.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Position und Größe der Datums- / Zeitauswahl-Steuerelement ist.  
  
 `pParentWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt, das das übergeordnete Fenster des Steuerelement für die Datums- und Zeitauswahl. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt die Datums- / Zeitauswahl-Steuerelements Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Erstellung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>Erstellen Sie ein Datums- / Zeitauswahl-Steuerelement  
  
1.  Rufen Sie [CDateTimeCtrl](#cdatetimectrl) zum Erstellen einer `CDateTimeCtrl` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die die Windows Datums- und Zeitauswahl erstellt und fügt es der `CDateTimeCtrl` Objekt.  
  
 Beim Aufruf von **erstellen**, werden die allgemeinen Steuerelemente initialisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="a-namegetdatetimepickerinfoa--cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 Ruft Informationen über die aktuellen Datums- / Zeitauswahl.  
  
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
 Diese Methode sendet die [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`besteht, wird verwendet, um programmgesteuert auf das Steuerelement für die Datums- / Zeitauswahl zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird gibt an, ob Informationen über die aktuellen Datums- / Zeitauswahl erfolgreich abgerufen.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="a-namegetmonthcalcolora--cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 Ruft die Farbe für einen bestimmten Teil des Monatskalender innerhalb der Datums- / Zeitauswahl-Steuerelement ab.  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `iColor`  
 Ein `int` -Wert, welcher Farbe Bereich des abzurufenden Monatskalender angibt. Eine Liste der Werte finden Sie unter der `iColor` -Parameter für [SetMonthCalColor](#setmonthcalcolor).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die Farbe-Einstellung für den angegebenen Teil des Monatskalender-Steuerelements im Erfolgsfall darstellt. Die Funktion gibt-1 zurück, wenn Fehler auftreten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="a-namegetmonthcalctrla--cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl:: GetMonthCalCtrl  
 Ruft die `CMonthCalCtrl` die Datums- / Zeitauswahl-Steuerelement zugeordnete Objekt.  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) -Objekt, oder **NULL** gelingt, oder wenn das Fenster nicht angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
 Steuerelemente für die Datums- / Zeitauswahl erstellen ein Monatskalender-Steuerelement untergeordnete klickt der Benutzer auf den Dropdown Pfeil. Wenn die `CMonthCalCtrl` Objekt ist nicht mehr erforderlich, es zerstört wird, damit Ihre Anwendung nicht angewiesen ist, auf das Speichern des Objekts, das die Datums-/ Zeitauswahl-Steuerelement des untergeordneten-Monats-Kalender darstellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="a-namegetmonthcalfonta--cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 Ruft die derzeit von Datum und Zeit-Auswahlsteuerelement Monatskalender-Steuerelement verwendete Schriftart ab.  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) -Objekt, oder **NULL** gelingt.  
  
### <a name="remarks"></a>Hinweise  
 Das `CFont` Objekt, auf das durch den Rückgabewert ist ein temporäres Objekt und wird während der nächsten Verarbeitung Leerlaufzeit zerstört.  
  
##  <a name="a-namegetmonthcalstylea--cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 Ruft den Stil der Dropdown-Monatskalender-Steuerelement, das das aktuelle Datums- / Zeitauswahl-Steuerelement zugeordnet ist.  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stil, der im Dropdown-Monatskalender-Steuerelement, das eine bitweise Kombination (oder) der Datums- / Zeitauswahl-Steuerelementtypen. Weitere Informationen finden Sie unter [Month Calendar-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb760919).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetrangea--cdatetimectrlgetrange"></a><a name="getrange"></a>CDateTimeCtrl::GetRange  
 Ruft die aktuellen Minimal- und Maximalwerte Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement zulässig.  
  
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
 Ein Zeiger auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das das früheste zulässige enthält die `CDateTimeCtrl` Objekt.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` Objekt oder ein `CTime` -Objekt, das die neuesten Frist enthält die `CDateTimeCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert mit Flags, die angeben, welche Bereiche festgelegt werden. If  
  
 `return value & GDTR_MAX` == 0  
  
 der zweite Parameter gültig ist. Auf ähnliche Weise, wenn  
  
 `return value & GDTR_MIN` == 0  
  
 der erste Parameter gültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In der MFC-Implementierung, geben Sie `COleDateTime` oder `CTime` Verwendungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="a-namegettimea--cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::GetTime  
 Ruft die derzeit ausgewählten Uhrzeit aus einem Datums- / Zeitauswahl-Steuerelement ab und fügt es in einem angegebenen `SYSTEMTIME` Struktur.  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *timeDest*  
 In der ersten Version, die einen Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das die Zeitinformationen System erhalten. In der zweiten Version, die einen Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das die Zeitinformationen System erhalten.  
  
 *pTimeDest*  
 Ein Zeiger auf die [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, um die Systeminformationen für die Zeit zu erhalten. Sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Version, die einen Wert ungleich NULL, wenn die Zeit erfolgreich, um geschrieben werden die `COleDateTime` -Objekt, andernfalls 0. In der zweiten und dritten Versionen einer `DWORD` gleich der **DwFlag** Elementgruppe der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Struktur. Finden Sie unter der **Hinweise** Beispielabschnitt unten für Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In der MFC-Implementierung von **GetTime**, können Sie `COleDateTime` oder `CTime` Klassen, oder Sie können eine `SYSTEMTIME` -Struktur, die Informationen zu speichern.  
  
 Der Rückgabewert `DWORD` in der zweiten und dritten Versionen oben gibt an, ob das Steuerelement für die Datums- / Zeitauswahl den Status "kein Datum" festgelegt ist wie in der [NMDATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761730) Strukturmember `dwFlags`. Wenn der Rückgabewert gleich **GDT_NONE**, das Steuerelement auf den Status "kein Datum" festgelegt ist und verwendet die **DTS_SHOWNONE** Stil. Wenn der Rückgabewert gleich **GDT_VALID**, die Systemzeit ist erfolgreich auf dem Zieldatenträger gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="a-namegetidealsizea--cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 Gibt die ideale Größe der Datums- / Zeitauswahl, die erforderlich sind, um das aktuelle Datum oder die Uhrzeit anzuzeigen.  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `psize`|Zeiger auf eine [Größe](http://msdn.microsoft.com/library/windows/desktop/dd145106) -Struktur, die ideale Größe für das Steuerelement enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist immer `true`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`besteht, wird verwendet, um programmgesteuert auf das Steuerelement für die Datums- / Zeitauswahl zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft die ideale Größe zum Anzeigen von Datums- / Zeitauswahl-Steuerelement ab.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="a-namesetformata--cdatetimectrlsetformat"></a><a name="setformat"></a>CDateTimeCtrl:: setFormat initialisiert  
 Legt die Anzeige eines Steuerelements in Übereinstimmung mit einer angegebenen Formatzeichenfolge für Datums- und Zeitauswahl.  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrFormat*  
 Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den gewünschten Anzeige definiert. Wenn dieser Parameter auf **NULL** setzt das Steuerelement auf die Standard-Formatzeichenfolge für das aktuelle Format.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
> [!NOTE]
>  Benutzereingaben bestimmt nicht Erfolg oder Fehler für diesen Aufruf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&6;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="a-namesetmonthcalcolora--cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 Legt die Farbe für einen bestimmten Teil des Monatskalender in einem Datums- / Zeitauswahl-Steuerelement fest.  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Parameter  
 `iColor`  
 `int`Wert, welcher Bereich eines Monatskalender-Steuerelements festlegen angibt. Dieser Wert kann eine der folgenden sein.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|MCSC_BACKGROUND|Legen Sie die Hintergrundfarbe, die zwischen Monaten angezeigt.|  
|MCSC_MONTHBK|Legen Sie die Hintergrundfarbe in einem Monat angezeigt.|  
|MCSC_TEXT|Legen Sie die Farbe für Text in einem Monat angezeigt.|  
|MCSC_TITLEBK|Legen Sie die Hintergrundfarbe im Titel des Kalenders angezeigt.|  
|MCSC_TITLETEXT|Legen Sie die Farbe für den Text innerhalb des Kalenders Titel anzuzeigen.|  
|MCSC_TRAILINGTEXT|Legen Sie die Farbe, die zum Anzeigen von Kopf- und nachfolgende Tag Text. Header und die nachfolgenden Tage werden die Tage aus dem vorherigen und folgenden Monate, die auf dem aktuellen Kalender angezeigt werden.|  
  
 `ref`  
 Ein **COLORREF** -Wert für die Farbe, die für den angegebenen Bereich eines Monatskalender festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die vorherige Einstellung der Farbe für den angegebenen Teil der im Monatskalender-Steuerelement im Erfolgsfall darstellt. Die Nachricht zurückgegeben, andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor).  
  
##  <a name="a-namesetmonthcalfonta--cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl:: SetMonthCalFont  
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
 Gibt an, ob das Steuerelement sofort neu soll beim Festlegen der Schrift gezeichnet werden. Wenn dieser Parameter auf **TRUE** bewirkt, dass das Steuerelement neu gezeichnet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#7;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  Wenn Sie diesen Code verwenden, sollten Sie ein Mitglied zu Ihrem `CDialog`-abgeleitete Klasse mit dem Namen `m_MonthFont` des Typs **CFont**.  
  
##  <a name="a-namesetmonthcalstylea--cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 Legt das Format des im Dropdown-Monatskalender-Steuerelement, das das aktuelle Datums- / Zeitauswahl-Steuerelement zugeordnet ist.  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwStyle`|Einen neuen Monat des Kalenders Format des Steuerelements, die eine bitweise Kombination (OR) Month Calendar-Steuerelementstile ist. Weitere Informationen finden Sie unter [Month Calendar-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb760919).|  
  
### <a name="return-value"></a>Rückgabewert  
 Das vorherige Format des im Dropdown-Monatskalender-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_dateTimeCtrl`besteht, wird verwendet, um programmgesteuert auf das Steuerelement für die Datums- / Zeitauswahl zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Datums- / Zeitauswahl-Steuerelement Wochennummern, abgekürzten Namen der Wochentage und kein heute Indikator angezeigt.  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1&3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="a-namesetrangea--cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl::SetRange  
 Legt die minimale und maximale zulässige Systemzeiten für einen Datums- / Zeitauswahl-Steuerelement fest.  
  
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
 Ein Zeiger auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das das früheste zulässige enthält die `CDateTimeCtrl` Objekt.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` Objekt oder ein `CTime` -Objekt, das die neuesten Frist enthält die `CDateTimeCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In der MFC-Implementierung, geben Sie `COleDateTime` oder `CTime` Verwendungen. Wenn die `COleDateTime` Objekt verfügt über eine **NULL** Status, der Bereich entfernt werden. Wenn die `CTime` Zeiger oder `COleDateTime` Zeiger **NULL**, der Bereich entfernt werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CDateTimeCtrl::GetRange](#getrange).  
  
##  <a name="a-namesettimea--cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::SetTime  
 Legt die Zeit in einem Datums- / Zeitauswahl-Steuerelement fest.  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *timeNew*  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) mit der auf das Steuerelement festgelegt wird.  
  
 *pTimeNew*  
 In der zweiten Version über einen Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, enthält die Zeit, zu dem das Steuerelement festgelegt werden. In der dritten Version über einen Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, enthält die Zeit, zu dem das Steuerelement festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In der MFC-Implementierung von **SetTime**, können Sie die `COleDateTime` oder `CTime` Klassen, oder Sie können eine `SYSTEMTIME` -Struktur, um die Informationen festzulegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#8;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl-Klasse](../../mfc/reference/cmonthcalctrl-class.md)

