---
title: CMonthCalCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonthCalCtrl
dev_langs:
- C++
helpviewer_keywords:
- month calendar controls, CMonthCalCtrl class
- common controls, Internet Explorer 4.0
- CMonthCalCtrl class
- Internet Explorer 4.0 common controls
- month calendar controls
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
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
ms.openlocfilehash: 96cefbeb7692a07088f596fe08fec2bf179b98bc
ms.lasthandoff: 02/24/2017

---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl-Klasse
Kapselt die Funktionalität eines Monatskalender-Steuerelements.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|Erstellt ein `CMonthCalCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMonthCalCtrl::Create](#create)|Erstellt ein Monatskalender-Steuerelement und fügt es der `CMonthCalCtrl` Objekt.|  
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|Ruft die Breite des Rahmens im aktuellen Monatskalender-Steuerelement ab.|  
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|Ruft die Anzahl der Kalender, die in der aktuellen Monatskalender-Steuerelement angezeigt.|  
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|Ruft Informationen über die aktuelle Monatskalender-Steuerelement.|  
|[CMonthCalCtrl::GetCalID](#getcalid)|Ruft den Kalender für die aktuelle Monatskalender-Steuerelement.|  
|[CMonthCalCtrl::GetColor](#getcolor)|Ruft die Farbe eines angegebenen Bereichs für ein Monatskalender-Steuerelement.|  
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|Ruft die Ansicht, die derzeit im aktuellen Monatskalender-Steuerelement angezeigt.|  
|[CMonthCalCtrl::GetCurSel](#getcursel)|Ruft die Systemzeit ab, wie durch das aktuell ausgewählte Datum.|  
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|Ruft den ersten Tag der Woche, in der am weitesten links stehende Spalte des Kalenders angezeigt werden.|  
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|Ruft die aktuelle maximale Anzahl von Tagen, die in einem Monatskalender-Steuerelement ausgewählt werden können.|  
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|Ruft die maximale Breite der Zeichenfolge "Heute" für das aktuelle Monatskalender-Steuerelement ab.|  
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|Ruft die minimale Größe erforderlich, um ein vollständiger Monat in einem Monatskalender-Steuerelement ab.|  
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|Ruft die Bildlaufrate für ein Monatskalender-Steuerelement ab.|  
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|Ruft das Datum Informationen, die die obere und untere Grenzwerte der Anzeige des Monatskalender-Steuerelements darstellt.|  
|[CMonthCalCtrl::GetRange](#getrange)|Ruft die aktuellen Minimal- und Maximalwerte Datumsangaben in einem Monatskalender-Steuerelement festlegen.|  
|[CMonthCalCtrl::GetSelRange](#getselrange)|Ruft Datumsinformationen, die die obere und untere Grenzwerte für den aktuell vom Benutzer ausgewählten Datumsbereich darstellt.|  
|[CMonthCalCtrl::GetToday](#gettoday)|Ruft die Datumsinformationen für das Datum als "heute" für ein Monatskalender-Steuerelement ab.|  
|[CMonthCalCtrl::HitTest](#hittest)|Bestimmt, welcher Abschnitt des Monatskalender-Steuerelements an einem bestimmten Punkt auf dem Bildschirm.|  
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|Gibt an, ob die aktuelle Ansicht der aktuellen Monatskalender-Steuerelements Jahrhundert ist.|  
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|Gibt an, ob die aktuelle Ansicht der aktuellen Monatskalender-Steuerelements Jahrzehnt ist.|  
|[CMonthCalCtrl::IsMonthView](#ismonthview)|Gibt an, ob die aktuelle Ansicht im aktuellen Monatskalender-Steuerelement im Monat angezeigt wird.|  
|[CMonthCalCtrl::IsYearView](#isyearview)|Gibt an, ob die aktuelle Ansicht der aktuellen Monatskalender-Steuerelements Jahr ist.|  
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|Legt die Breite des Rahmens im aktuellen Monatskalender-Steuerelement fest.|  
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|Legt die Standardbreite des Rahmens im aktuellen Monatskalender-Steuerelement fest.|  
|[CMonthCalCtrl::SetCalID](#setcalid)|Legt den Kalender Bezeichner für das aktuelle Monatskalender-Steuerelement.|  
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|Legt das aktuelle Monatskalender-Steuerelement um Jahrhundert anzuzeigen.|  
|[CMonthCalCtrl::SetColor](#setcolor)|Legt die Farbe eines angegebenen Bereichs des Monatskalender-Steuerelements fest.|  
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|Legt das aktuelle Monatskalender-Steuerelement zum Anzeigen der angegebenen Ansicht.|  
|[CMonthCalCtrl::SetCurSel](#setcursel)|Legt fest, das derzeit ausgewählte Datum für ein Monatskalender-Steuerelement.|  
|[CMonthCalCtrl:: SetDayState](#setdaystate)|Legt die Anzeige für Tage in einem Monatskalender-Steuerelement fest.|  
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|Legt den aktuellen Monatskalender-Steuerelement anzuzeigende Jahrzehnt.|  
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|Legt den Tag der Woche, in der am weitesten links stehende Spalte des Kalenders angezeigt werden.|  
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|Legt die maximale Anzahl von Tagen, die in einem Monatskalender-Steuerelement ausgewählt werden können.|  
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|Legt die Bildlaufrate für ein Monatskalender-Steuerelement.|  
|[CMonthCalCtrl::SetMonthView](#setmonthview)|Legt das aktuelle Monatskalender-Steuerelement um Monat anzuzeigen.|  
|[CMonthCalCtrl::SetRange](#setrange)|Legt das Minimum und das maximal zulässige Datum für ein Monatskalender-Steuerelement.|  
|[CMonthCalCtrl::SetSelRange](#setselrange)|Legt die Auswahl für ein Monatskalender-Steuerelement auf einen bestimmten Zeitraum hinweg.|  
|[CMonthCalCtrl::SetToday](#settoday)|Legt das Kalender-Steuerelement für den aktuellen Tag.|  
|[CMonthCalCtrl::SetYearView](#setyearview)|Legt den aktuellen Monatskalender-Steuerelement auf Jahr anzeigen.|  
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|Zeichnet das Monatskalender-Steuerelement die Größe Minimalwert, einen Monat.|  
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|Für die aktuelle Monatskalender-Steuerelement berechnet das kleinste Rechteck, das alle Kalender enthalten kann, die in einem angegebenen Rechteck zu passen.|  
  
## <a name="remarks"></a>Hinweise  
 Im Monatskalender-Steuerelement bietet dem Benutzer mit einer einfachen Kalender-Schnittstelle, von der der Benutzer ein Datum auswählen kann. Der Benutzer kann die Anzeige von ändern:  
  
-   Scrollen rückwärts und Vorwärts, von Monat zu Monat.  
  
-   Auf den Text der heute, um den aktuellen Tag (wenn der **MCS_NOTODAY** Stil wird nicht verwendet).  
  
-   Auswählen eines Monats oder eines Jahres in einem Popup-Menü.  
  
 Sie können anpassen, den Monat Monatskalender-Steuerelement durch eine Vielzahl von Formaten auf das Objekt angewendet werden, bei der Erstellung. Diese Stile werden im Abschnitt [Month Calendar-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb760919) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Im Monatskalender-Steuerelement kann mehr als einen Monat angezeigt, und es kann Tage (z. B. Feiertage) angeben, durch Fettdruck zu setzen das Datum.  
  
 Weitere Informationen zur Verwendung der im Monatskalender-Steuerelements finden Sie unter [Verwenden von CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdtctl.h  
  
##  <a name="a-namecmonthcalctrla--cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a>CMonthCalCtrl::CMonthCalCtrl  
 Erstellt ein `CMonthCalCtrl`-Objekt.  
  
```  
CMonthCalCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen **erstellen** nach dem Erstellen des Objekts.  
  
##  <a name="a-namecreatea--cmonthcalctrlcreate"></a><a name="create"></a>CMonthCalCtrl::Create  
 Erstellt ein Monatskalender-Steuerelement und fügt es der `CMonthCalCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);

 
virtual BOOL Create(
    DWORD dwStyle,  
    const POINT& pt,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Kombination von Windows-Stile im Monatskalender-Steuerelement angewendet. Finden Sie unter [Month Calendar-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb760919) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zu den.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur. Enthält die Position und Größe der im Monatskalender-Steuerelement.  
  
 `pt`  
 Ein Verweis auf eine [Punkt](http://msdn.microsoft.com/library/windows/desktop/dd162805) -Struktur, die den Speicherort der im Monatskalender-Steuerelement angibt.  
  
 `pParentWnd`  
 Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Monatskalender-Steuerelements ist. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt die ID der im Monatskalender-Steuerelement des Steuerelements an  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie einen Monat Monatskalender-Steuerelement in zwei Schritten:  
  
1.  Rufen Sie [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) zum Erstellen einer `CMonthCalCtrl` Objekt.  
  
2.  Rufen Sie diese Memberfunktion, die ein Monatskalender-Steuerelement erstellt, und fügt es der `CMonthCalCtrl` Objekt.  
  
 Beim Aufruf von **erstellen**, werden die allgemeinen Steuerelemente initialisiert. Die Version des **erstellen** Sie Aufruf bestimmt, wie es angepasst wird:  
  
-   Um MFC automatisch die Größe des Steuerelements ein Monat, die Überschreibung, die mithilfe der `pt` Parameter.  
  
-   Um die Größe des Steuerelements selbst, die Überschreibung dieser Funktion, die mithilfe der `rect` Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#1;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]  
  
##  <a name="a-namegetcalendarbordera--cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a>CMonthCalCtrl::GetCalendarBorder  
 Ruft die Breite des Rahmens im aktuellen Monatskalender-Steuerelement ab.  
  
```  
int GetCalendarBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des Steuerelementrahmens in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760945) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcalendarcounta--cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a>CMonthCalCtrl::GetCalendarCount  
 Ruft die Anzahl der Kalender, die in der aktuellen Monatskalender-Steuerelement angezeigt.  
  
```  
int GetCalendarCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Kalender, die momentan in der im Monatskalender-Steuerelement angezeigt. Die maximale zulässige Anzahl von Kalendern ist 12.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCALENDARCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760947) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcalendargridinfoa--cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a>CMonthCalCtrl::GetCalendarGridInfo  
 Ruft Informationen über die aktuelle Monatskalender-Steuerelement.  
  
```  
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pmcGridInfo`|Zeiger auf eine [MCGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760925) -Struktur, die Informationen über die aktuelle Monatskalender-Steuerelement empfängt. Der Aufrufer ist verantwortlich für das zuordnen und diese Struktur zu initialisieren.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCALENDARGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760949) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `GetCalendarGridInfo` Methode, um das Kalenderdatum abzurufen, die im aktuellen Monatskalender-Steuerelement anzeigt.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1&3;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]  
  
##  <a name="a-namegetcalida--cmonthcalctrlgetcalid"></a><a name="getcalid"></a>CMonthCalCtrl::GetCalID  
 Ruft den Kalender für die aktuelle Monatskalender-Steuerelement.  
  
```  
CALID GetCalID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eines der [Kalender Bezeichner](http://msdn.microsoft.com/library/windows/desktop/dd317732) Konstanten.  
  
### <a name="remarks"></a>Hinweise  
 Ein Kalender Bezeichner kennzeichnet einen regionsspezifische Kalender, z. B. die Gregorianisch (lokalisiert), Japanisch oder Hijri Kalender. Die Anwendung kann einen Kalender Bezeichner verwenden, der verschiedene Funktionen unterstützen die Sprache ist.  
  
 Diese Methode sendet die [MCM_GETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760951) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetcolora--cmonthcalctrlgetcolor"></a><a name="getcolor"></a>CMonthCalCtrl::GetColor  
 Ruft die Farbe des Bereichs des Monats Monatskalender-Steuerelements, die durch angegebene `nRegion`.  
  
```  
COLORREF GetColor(int nRegion) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nRegion`  
 Der Bereich, der im Monatskalender-Steuerelement aus dem die Farbe abgerufen werden. Eine Liste der Werte finden Sie unter der `nRegion` Parameter der [SetColor](#setcolor).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Wert, der Teil im Monatskalender-Steuerelement, zugeordnete Farbe angibt, bei Erfolg. Diese Memberfunktion gibt, andernfalls-1 zurück.  
  
##  <a name="a-namegetcurrentviewa--cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a>CMonthCalCtrl::GetCurrentView  
 Ruft die Ansicht, die derzeit im aktuellen Monatskalender-Steuerelement angezeigt.  
  
```  
DWORD GetCurrentView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Ansicht der durch einen der folgenden Werte angegeben wird:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`MCMV_MONTH`|Monatliche Ansicht|  
|`MCMV_YEAR`|Jährliche Ansicht|  
|`MCMV_DECADE`|Jahrzehnt anzeigen|  
|`MCMV_CENTURY`|Jahrhundert anzeigen|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Beispiel  
 Die folgenden Code-Beispiel-Berichte anzeigen Monatskalender-Steuerelement derzeit zeigt.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]  
  
##  <a name="a-namegetcursela--cmonthcalctrlgetcursel"></a><a name="getcursel"></a>CMonthCalCtrl::GetCurSel  
 Ruft die Systemzeit ab, wie durch das aktuell ausgewählte Datum.  
  
```  
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;  
   
BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `refDateTime`  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt oder ein [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt. Erhält die aktuelle Zeit.  
  
 `pDateTime`  
 Ein Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die die aktuell ausgewählte Datumsinformationen erhält. Dieser Parameter muss eine gültige Adresse sein und darf nicht sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; Otherwize 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb760957)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Diese Memberfunktion schlägt fehl, wenn das Format **MCS_MULTISELECT** festgelegt ist.  
  
 In MFC Implementierung von `GetCurSel`, können Sie angeben, eine `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
##  <a name="a-namegetfirstdayofweeka--cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a>CMonthCalCtrl::GetFirstDayOfWeek  
 Ruft den ersten Tag der Woche, in der am weitesten links stehende Spalte des Kalenders angezeigt werden.  
  
```  
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pbLocal*  
 Ein Zeiger auf eine **BOOL** Wert. Wenn der Wert ungleich NULL ist, entspricht die Einstellung des Steuerelements nicht die Einstellung in der Systemsteuerung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ganzzahlwert, der den ersten Tag der Woche darstellt. Finden Sie unter **Hinweise** für Weitere Informationen zur Bedeutung dieser Ganzzahlen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb760958), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Die Wochentage werden als Ganzzahlen dargestellt.  
  
|Wert|Tag der Woche|  
|-----------|---------------------|  
|0|Montag|  
|1|Dienstag|  
|2|Mittwoch|  
|3|Donnerstag|  
|4|Freitag|  
|5|Samstag|  
|6|Sonntag|  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek).  
  
##  <a name="a-namegetmaxselcounta--cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a>CMonthCalCtrl::GetMaxSelCount  
 Ruft die aktuelle maximale Anzahl von Tagen, die in einem Monatskalender-Steuerelement ausgewählt werden können.  
  
```  
int GetMaxSelCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ganzzahlwert, der die Gesamtanzahl von Tagen ausgewählt werden können, die für das Steuerelement darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760960)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Verwenden Sie diese Memberfunktion für Steuerelemente mit den **MCS_MULTISELECT** Set formatieren.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMonthCalCtrl::SetMaxSelCount](#setmaxselcount).  
  
##  <a name="a-namegetmaxtodaywidtha--cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a>CMonthCalCtrl::GetMaxTodayWidth  
 Ruft die maximale Breite der Zeichenfolge "Heute" für das aktuelle Monatskalender-Steuerelement ab.  
  
```  
DWORD GetMaxTodayWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Zeichenfolge "Heute" in Pixel.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `GetMaxTodayWidth` Methode.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer kann auf das aktuelle Datum zurück, durch Klicken auf die Zeichenfolge "Heute", die am unteren Rand der im Monatskalender-Steuerelement angezeigt wird. Die Zeichenfolge "Heute" enthält Bezeichnungstext und Textformat.  
  
 Diese Methode sendet die [MCM_GETMAXTODAYWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760962) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetminreqrecta--cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a>CMonthCalCtrl::GetMinReqRect  
 Ruft die minimale Größe erforderlich, um ein vollständiger Monat in einem Monatskalender-Steuerelement ab.  
  
```  
BOOL GetMinReqRect(RECT* pRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pRect`  
 Ein Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die umschließende Rechteck Informationen erhalten. Dieser Parameter muss eine gültige Adresse sein und darf nicht sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, diese Member-Funktion einen Wert ungleich NULL zurückgibt und `lpRect` empfängt die entsprechenden Bindungsinformationen. Die Member-Funktion gibt 0 zurück, wenn dies nicht gelingt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMINREQRECT](http://msdn.microsoft.com/library/windows/desktop/bb760978), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmonthdeltaa--cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a>CMonthCalCtrl::GetMonthDelta  
 Ruft die Bildlaufrate für ein Monatskalender-Steuerelement ab.  
  
```  
int GetMonthDelta() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Bildlaufrate für das Monatskalender-Steuerelement. Die Bildlaufrate ist die Anzahl der Monate, dass das Steuerelement die Anzeige klickt der Benutzer auf eine Bildlaufschaltfläche einmal verschoben wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb760980), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetmonthrangea--cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a>CMonthCalCtrl::GetMonthRange  
 Ruft das Datum Informationen, die die obere und untere Grenzwerte der Anzeige des Monatskalender-Steuerelements darstellt.  
  
```  
int GetMonthRange(
    COleDateTime& refMinRange,  
    COleDateTime& refMaxRange,  
    DWORD dwFlags) const;  
  
int GetMonthRange(
    CTime& refMinRange,  
    CTime& refMaxRange,  
    DWORD dwFlags) const;  
  
int GetMonthRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange,  
    DWORD dwFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `refMinRange`  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das minimale zulässige Datum enthält.  
  
 `refMaxRange`  
 Ein Verweis auf eine `COleDateTime` oder `CTime` -Objekt, das maximal zulässige Datum enthält.  
  
 `pMinRange`  
 Ein Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `SYSTEMTIME` -Struktur, die das Datum am höchsten Ende des Bereichs enthält.  
  
 `dwFlags`  
 Wert, die Angabe des Bereichs der die Bereichsgrenzen abgerufen werden sollen. Dieser Wert muss eine der folgenden sein.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|GMR_DAYSTATE|Einschließen von vorangestellten und nachfolgenden Monate des sichtbaren Bereichs, die nur teilweise angezeigt werden.|  
|GMR_VISIBLE|Enthalten Sie nur diese Monate an, die vollständig angezeigt werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Ganzzahl des Bereichs in Monaten über die beiden Grenzwerte erstreckt erkennbar `refMinRange` und `refMaxRange` in der ersten und zweiten Version oder `pMinRange` und `pMaxRange` in der dritten Version.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETMONTHRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760981), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In MFC Implementierung von `GetMonthRange`, können Sie angeben, `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMonthCalCtrl:: SetDayState](#setdaystate).  
  
##  <a name="a-namegetrangea--cmonthcalctrlgetrange"></a><a name="getrange"></a>CMonthCalCtrl::GetRange  
 Ruft die aktuellen Minimal- und Maximalwerte Datumsangaben in einem Monatskalender-Steuerelement festlegen.  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
  
DWORD GetRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pMinRange`  
 Ein Zeiger auf eine `COleDateTime` -Objekt, ein `CTime` -Objekt, oder [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` -Objekt, ein `CTime` -Objekt, oder [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am höchsten Ende des Bereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` ,&0; (null) sein kann (es sind keine Grenzwerte festgelegt) oder eine Kombination der folgenden Werte, die Grenze angeben.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|GDTR_MAX|Maximale wird für das Steuerelement festgelegt. `pMaxRange` gültig ist und die entsprechenden Datumsinformationen enthält.|  
|GDTR_MIN|Eine Mindestanzahl wird für das Steuerelement festgelegt. `pMinRange` gültig ist und die entsprechenden Datumsinformationen enthält.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760983), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In MFC Implementierung von `GetRange`, können Sie angeben, eine `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#2;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]  
  
##  <a name="a-namegetselrangea--cmonthcalctrlgetselrange"></a><a name="getselrange"></a>CMonthCalCtrl::GetSelRange  
 Ruft Datumsinformationen, die die obere und untere Grenzwerte für den aktuell vom Benutzer ausgewählten Datumsbereich darstellt.  
  
```  
BOOL GetSelRange(
    COleDateTime& refMinRange,  
    COleDateTime& refMaxRange) const;  
  
BOOL GetSelRange(
    CTime& refMinRange,  
    CTime& refMaxRange) const;  
  
BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,  
    LPSYSTEMTIME pMaxRange) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `refMinRange`  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt, das minimale zulässige Datum enthält.  
  
 `refMaxRange`  
 Ein Verweis auf eine `COleDateTime` oder `CTime` -Objekt, das maximal zulässige Datum enthält.  
  
 `pMinRange`  
 Ein Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `SYSTEMTIME` -Struktur, die das Datum am höchsten Ende des Bereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760985), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. `GetSelRange`schlägt fehl, wenn auf ein Monatskalender-Steuerelement angewendet wird, die nicht der **MCS_MULTISELECT** Stil.  
  
 In MFC Implementierung von `GetSelRange`, können Sie angeben, `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
##  <a name="a-namegettodaya--cmonthcalctrlgettoday"></a><a name="gettoday"></a>CMonthCalCtrl::GetToday  
 Ruft die Datumsinformationen für das Datum als "heute" für ein Monatskalender-Steuerelement ab.  
  
```  
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;  
   
BOOL GetToday(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `refDateTime`  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, das den aktuellen Tag angibt.  
  
 `pDateTime`  
 Ein Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die die Datumsangaben zu erhalten. Dieser Parameter muss eine gültige Adresse sein und darf nicht sein **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_GETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb760987), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In MFC Implementierung von `GetToday`, können Sie angeben, eine `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&3;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]  
  
##  <a name="a-namehittesta--cmonthcalctrlhittest"></a><a name="hittest"></a>CMonthCalCtrl::HitTest  
 Bestimmt, welche Monatskalender-Steuerelement, ob vorhanden, an der angegebenen Position.  
  
```  
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```  
  
### <a name="parameters"></a>Parameter  
 *pMCHitTest*  
 Ein Zeiger auf eine [MCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760927) Struktur mit Treffertests für das Monatskalender-Steuerelement verweist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD`-Wert. Gleich der **uHit** Mitglied der **MCHITTESTINFO** Struktur.  
  
### <a name="remarks"></a>Hinweise  
 `HitTest`verwendet die **MCHITTESTINFO** -Struktur, die Informationen zu den Treffertest enthält.  
  
##  <a name="a-nameiscenturyviewa--cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a>CMonthCalCtrl::IsCenturyView  
 Gibt an, ob die aktuelle Ansicht der aktuellen Monatskalender-Steuerelements Jahrhundert ist.  
  
```  
BOOL IsCenturyView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die aktuelle Ansicht Jahrhundert ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn die Nachricht gibt `MCMV_CENTURY`, gibt diese Methode `true`.  
  
##  <a name="a-nameisdecadeviewa--cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a>CMonthCalCtrl::IsDecadeView  
 Gibt an, ob die aktuelle Ansicht der aktuellen Monatskalender-Steuerelements Jahrzehnt ist.  
  
```  
BOOL IsDecadeView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die aktuelle Ansicht die zehn Jahre ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn die Nachricht gibt `MCMV_DECADE`, gibt diese Methode `true`.  
  
##  <a name="a-nameismonthviewa--cmonthcalctrlismonthview"></a><a name="ismonthview"></a>CMonthCalCtrl::IsMonthView  
 Gibt an, ob die aktuelle Ansicht im aktuellen Monatskalender-Steuerelement im Monat angezeigt wird.  
  
```  
BOOL IsMonthView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die aktuelle Ansicht der Monat ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn die Nachricht gibt `MCMV_MONTH`, gibt diese Methode `true`.  
  
##  <a name="a-nameisyearviewa--cmonthcalctrlisyearview"></a><a name="isyearview"></a>CMonthCalCtrl::IsYearView  
 Gibt an, ob die aktuelle Ansicht der aktuellen Monatskalender-Steuerelements Jahr ist.  
  
```  
BOOL IsYearView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die aktuelle Ansicht Jahr ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Wenn die Nachricht gibt `MCMV_YEAR`, gibt diese Methode `true`.  
  
##  <a name="a-namesetcalendarbordera--cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a>CMonthCalCtrl::SetCalendarBorder  
 Legt die Breite des Rahmens im aktuellen Monatskalender-Steuerelement fest.  
  
```  
void SetCalendarBorder(int cxyBorder);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `cxyBorder`|Die Breite des Rahmens in Pixel.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode erfolgreich ist, wird die Breite des Rahmens festlegen, zu der `cxyBorder` Parameter. Andernfalls wird die Breite des Rahmens auf den Standardwert, der vom aktuellen angegeben wird zurückgesetzt [Design](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), oder&0;, wenn Designs nicht verwendet werden.  
  
 Diese Methode sendet die [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgenden Codebeispiel wird die Breite des Rahmens des Monatskalender Steuern auf acht Pixel. Verwenden der [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder) Methode, um zu bestimmen, ob diese Methode erfolgreich ausgeführt wurde.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1&6;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]  
  
##  <a name="a-namesetcalendarborderdefaulta--cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a>CMonthCalCtrl::SetCalendarBorderDefault  
 Legt die Standardbreite des Rahmens im aktuellen Monatskalender-Steuerelement fest.  
  
```  
void SetCalendarBorderDefault();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Breite des Rahmens, der angegebene vom aktuellen Standardwert festgelegt ist [Design](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx), oder&0;, wenn Designs nicht verwendet werden.  
  
 Diese Methode sendet die [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcalida--cmonthcalctrlsetcalid"></a><a name="setcalid"></a>CMonthCalCtrl::SetCalID  
 Legt den Kalender Bezeichner für das aktuelle Monatskalender-Steuerelement.  
  
```  
BOOL SetCalID(CALID calid);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `calid`|Eines der [Kalender Bezeichner](http://msdn.microsoft.com/library/windows/desktop/dd317732) Konstanten.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Kalender Bezeichner gibt einen regionsspezifische Kalender, z. B. die Gregorianisch (lokalisiert), Japanisch oder Hijri Kalender. Verwenden der `SetCalID` Methode, um einen Kalender anzuzeigen, die durch angegeben ist die `calid` -Parameters, wenn das Gebietsschema mit dem Kalender auf Ihrem Computer installiert ist.  
  
 Diese Methode sendet die [MCM_SETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760995) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird im Monatskalender-Steuerelement den Kalender Japan Zeitraum anzeigen. Die `SetCalID` Methode erfolgreich ist, nur dann, wenn Sie diesen Kalender auf Ihrem Computer installiert ist.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]  
  
##  <a name="a-namesetcenturyviewa--cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a>CMonthCalCtrl::SetCenturyView  
 Legt das aktuelle Monatskalender-Steuerelement um Jahrhundert anzuzeigen.  
  
```  
BOOL SetCenturyView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht auf festgelegt `MCMV_CENTURY`, die die Sicht Jahrhundert darstellt.  
  
##  <a name="a-namesetcolora--cmonthcalctrlsetcolor"></a><a name="setcolor"></a>CMonthCalCtrl::SetColor  
 Legt die Farbe eines angegebenen Bereichs des Monatskalender-Steuerelements fest.  
  
```  
COLORREF SetColor(
    int nRegion,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>Parameter  
 `nRegion`  
 Eine ganze Zahl, welche Monat Kalenderfarbe festlegen angibt. Dieser Wert kann eine der folgenden sein.  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|MCSC_BACKGROUND|Die Hintergrundfarbe, die zwischen Monaten angezeigt.|  
|MCSC_MONTHBK|Die Hintergrundfarbe, in der der Monat angezeigt wird.|  
|MCSC_TEXT|Die Farbe, in der Text in einem Monat angezeigt wird.|  
|MCSC_TITLEBK|Die Hintergrundfarbe, in der die Kalenderüberschrift angezeigt wird.|  
|MCSC_TITLETEXT|Die Farbe, in der der Text in der Kalenderüberschrift angezeigt wird.|  
|MCSC_TRAILINGTEXT|Die Farbe, die zum Anzeigen von Kopf-und nachfolgende Tag verwendet. Header und die nachfolgenden Tage werden die Tage aus dem vorherigen und folgenden Monate, die auf dem aktuellen Kalender angezeigt werden.|  
  
 `ref`  
 Ein **COLORREF** Wert für die neue Farbe-Einstellung für den angegebenen Teil der im Monatskalender-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die vorherige Einstellung der Farbe für den angegebenen Teil des Monatskalender-Steuerelements, wenn erfolgreich darstellt. Andernfalls gibt diese Meldung-1 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760997), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&4;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]  
  
##  <a name="a-namesetcurrentviewa--cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a>CMonthCalCtrl::SetCurrentView  
 Legt das aktuelle Monatskalender-Steuerelement zum Anzeigen der angegebenen Ansicht.  
  
```  
BOOL SetCurrentView(DWORD dwNewView);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwNewView`|Einer der folgenden Werte, der angibt, ein monatlich, jährlich, zehn oder Jahrhundert anzeigen.<br /><br /> MCMV_MONTH: Monatliche Ansicht<br /><br /> MCMV_YEAR: Jährliche Ansicht<br /><br /> MCMV_DECADE: Jahrzehnt anzeigen<br /><br /> MCMV_CENTURY: Jahrhundert anzeigen|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [MCM_SETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760998) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcursela--cmonthcalctrlsetcursel"></a><a name="setcursel"></a>CMonthCalCtrl::SetCurSel  
 Legt fest, das derzeit ausgewählte Datum für ein Monatskalender-Steuerelement.  
  
```  
BOOL SetCurSel(const COleDateTime& refDateTime);  
BOOL SetCurSel(const CTime& refDateTime);  
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>Parameter  
 `refDateTime`  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) oder [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt, das das aktuell ausgewählte Monatskalender-Steuerelement angibt.  
  
 `pDateTime`  
 Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die das Datum als die aktuelle Auswahl festgelegten enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb761002), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In MFC Implementierung von `SetCurSel`, können Sie angeben, eine `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&5;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]  
  
##  <a name="a-namesetdaystatea--cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a>CMonthCalCtrl:: SetDayState  
 Legt die Anzeige für Tage in einem Monatskalender-Steuerelement fest.  
  
```  
BOOL SetDayState(
    int nMonths,  
    LPMONTHDAYSTATE pStates);
```  
  
### <a name="parameters"></a>Parameter  
 *nMonths*  
 Wert, der angibt, wie viele Elemente im Array enthalten sind, die `pStates` verweist.  
  
 `pStates`  
 Ein Zeiger auf eine [MONTHDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760915) Array von Werten, die definieren, wie im Monatskalender-Steuerelement, jeden Tag in der Anzeige gezeichnet wird. Die **MONTHDAYSTATE** Datentyp ist ein Bitfeld, in dem jedes Bit (1 bis 31) stellt den Zustand eines Tages eines Monats dar. Wenn eine Bit aktiviert ist, wird der entsprechende Tag angezeigt fett; Andernfalls wird es mit keine Hervorhebung angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761004), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&6;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]  
  
##  <a name="a-namesetdecadeviewa--cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a>CMonthCalCtrl::SetDecadeView  
 Legt den aktuellen Monatskalender-Steuerelement anzuzeigende Jahrzehnt.  
  
```  
BOOL SetDecadeView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht auf festgelegt `MCMV_DECADE`, die die Sicht Jahrzehnt darstellt.  
  
##  <a name="a-namesetfirstdayofweeka--cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a>CMonthCalCtrl::SetFirstDayOfWeek  
 Legt den Tag der Woche, in der am weitesten links stehende Spalte des Kalenders angezeigt werden.  
  
```  
BOOL SetFirstDayOfWeek(
    int iDay,  
    int* lpnOld = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *iDay*  
 Ein Ganzzahlwert, der den Tag darstellt, wird als erster Tag der Woche festgelegt werden. Dieser Wert muss eine der Nummern der Tag sein. Finden Sie unter [GetFirstDayOfWeek](#getfirstdayofweek) eine Beschreibung der Tageszahlen.  
  
 *lpnOld*  
 Ein Zeiger auf eine Ganzzahl, die den ersten Tag der Woche zuvor festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn ein Wert, der von der vorherige erste Tag der Woche festgelegt ist **LOCALE_IFIRSTDAYOFWEEK**, die den Tag in der Control Panel-Einstellung angegeben ist. Andernfalls gibt diese Funktion 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb761006), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#7;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]  
  
##  <a name="a-namesetmaxselcounta--cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a>CMonthCalCtrl::SetMaxSelCount  
 Legt die maximale Anzahl von Tagen, die in einem Monatskalender-Steuerelement ausgewählt werden können.  
  
```  
BOOL SetMaxSelCount(int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `nMax`  
 Der Wert, der die maximale Anzahl von Tagen ausgewählt dargestellt festgelegt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761008), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CMonthCalCtrl&#8;](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]  
  
##  <a name="a-namesetmonthdeltaa--cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a>CMonthCalCtrl::SetMonthDelta  
 Legt die Bildlaufrate für ein Monatskalender-Steuerelement.  
  
```  
int SetMonthDelta(int iDelta);
```  
  
### <a name="parameters"></a>Parameter  
 *iDelta*  
 Die Anzahl der Monate als Bildlaufrate für das Steuerelement festgelegt werden. Wenn dieser Wert&0; (null) ist, wird das Delta Monat standardmäßig auf zurückgesetzt, d. h. die Anzahl der Monate, die im Steuerelement angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Bildlaufrate. Wenn die Bildlaufrate zuvor nicht festgelegt wurde, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb761010), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetmonthviewa--cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a>CMonthCalCtrl::SetMonthView  
 Legt das aktuelle Monatskalender-Steuerelement um Monat anzuzeigen.  
  
```  
BOOL SetMonthView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht auf festgelegt `MCMV_MONTH`, die die Monatsansicht darstellt.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_monthCalCtrl`, d. h. mit der im Monatskalender-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird im Monatskalender-Steuerelement den Monat, Jahr, Jahrzehnt und Jahrhundert Ansichten angezeigt.  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]  
  
##  <a name="a-namesetrangea--cmonthcalctrlsetrange"></a><a name="setrange"></a>CMonthCalCtrl::SetRange  
 Legt die minimalen und maximalen zulässigen Daten für ein Monatskalender-Steuerelement.  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);

 
BOOL SetRange(
    const LPSYSTEMTIME pMinRange,  
    const LPSYSTEMTIME pMaxRange);
```  
  
### <a name="parameters"></a>Parameter  
 `pMinRange`  
 Ein Zeiger auf eine `COleDateTime` -Objekt, ein `CTime` -Objekt, oder [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` -Objekt, ein `CTime` -Objekt, oder `SYSTEMTIME` -Struktur, die das Datum am höchsten Ende des Bereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761012), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In MFC Implementierung von `SetRange`, können Sie angeben, `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMonthCalCtrl::GetRange](#getrange).  
  
##  <a name="a-namesetselrangea--cmonthcalctrlsetselrange"></a><a name="setselrange"></a>CMonthCalCtrl::SetSelRange  
 Legt die Auswahl für ein Monatskalender-Steuerelement auf einen bestimmten Zeitraum hinweg.  
  
```  
BOOL SetSelRange(
    const COleDateTime& pMinRange,  
    const COleDateTime& pMaxRange);

 
BOOL SetSelRange(
    const CTime& pMinRange,  
    const CTime& pMaxRange);

 
BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,  
    const LPSYSTEMTIME pMaxRange);
```  
  
### <a name="parameters"></a>Parameter  
 `pMinRange`  
 Ein Zeiger auf eine `COleDateTime` -Objekt, ein `CTime` -Objekt, oder [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das Datum am niedrigsten Ende des Bereichs enthält.  
  
 `pMaxRange`  
 Ein Zeiger auf eine `COleDateTime` -Objekt, ein `CTime` -Objekt, oder `SYSTEMTIME` -Struktur, die das Datum am höchsten Ende des Bereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761014), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. In MFC Implementierung von `SetSelRange`, können Sie angeben, `COleDateTime` Verwendung eine `CTime` Verwendung oder eine `SYSTEMTIME` Struktur Nutzung.  
  
##  <a name="a-namesettodaya--cmonthcalctrlsettoday"></a><a name="settoday"></a>CMonthCalCtrl::SetToday  
 Legt das Kalender-Steuerelement für den aktuellen Tag.  
  
```  
void SetToday(const COleDateTime& refDateTime);  
void SetToday(const CTime* pDateTime);  
  void SetToday(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>Parameter  
 `refDateTime`  
 Ein Verweis auf eine [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, das das aktuelle Datum enthält.  
  
 `pDateTime`  
 In der zweiten Version, die einen Zeiger auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt mit Informationen über das aktuelle Datum. In der dritten Version ist ein Zeiger auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die das aktuelle Datum enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [MCM_SETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb761016), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMonthCalCtrl::GetToday](#gettoday).  
  
##  <a name="a-namesetyearviewa--cmonthcalctrlsetyearview"></a><a name="setyearview"></a>CMonthCalCtrl::SetYearView  
 Legt den aktuellen Monatskalender-Steuerelement auf Jahr anzeigen.  
  
```  
BOOL SetYearView();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die [CMonthCalCtrl::SetCurrentView](#setcurrentview) Methode, um die Ansicht auf festgelegt `MCMV_YEAR`, der die jährliche Ansicht darstellt.  
  
##  <a name="a-namesizeminreqa--cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a>CMonthCalCtrl::SizeMinReq  
 Zeigt der Monat Monatskalender-Steuerelement die minimale Größe, einen Monat.  
  
```  
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bRepaint`  
 Gibt an, ob das Steuerelement neu gezeichnet wird. In der Standardeinstellung **TRUE**. Wenn **FALSE**, erfolgt keine Aktualisierung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Monatskalender-Steuerelement auf den Minimalwert festgelegt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `SizeMinReq` erfolgreich im gesamten Monatskalender-Steuerelement für ein Monatskalender angezeigt.  
  
##  <a name="a-namesizerecttomina--cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a>CMonthCalCtrl::SizeRectToMin  
 Für die aktuelle Monatskalender-Steuerelement berechnet das kleinste Rechteck, das alle Kalender enthalten kann, die in einem angegebenen Rechteck zu passen.  
  
```  
LPRECT SizeRectToMin(LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `lpRect`|Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die ein Rechteck definiert, die die gewünschte Anzahl der Kalender enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die ein Rechteck definiert, deren Größe kleiner oder gleich dem Rechteck definiert, durch die `lpRect` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet, wie viele Kalender im angegebenen Rechteck passt der `lpRect` -Parameter und gibt anschließend das kleinste Rechteck, das die Anzahl der Kalender enthalten kann. Tatsächlich verkleinert diese Methode das angegebene Rechteck angepasst, dass genau die gewünschte Anzahl von Kalendern.  
  
 Diese Methode sendet die [MCM_SIZERECTTOMIN](http://msdn.microsoft.com/library/windows/desktop/bb761020) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl-Klasse](../../mfc/reference/cdatetimectrl-class.md)

