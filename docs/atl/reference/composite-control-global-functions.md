---
title: Globale Funktionen zusammengesetztes Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c62d5056f28460644084296598ae865c6ff5f48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366600"
---
# <a name="composite-control-global-functions"></a>Globale Funktionen von zusammengesetzten Steuerelementen
Diese Funktionen bieten Unterstützung für das Erstellen von Dialogfeldern und zum Erstellen, hosten und Lizenzieren von ActiveX-Steuerelementen.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|Erstellt ein modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage. Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|Erstellt ein nicht modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage. Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Erstellt ein ActiveX-Steuerelement, initialisiert es im angegebenen Fenster gehostet und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es im angegebenen Fenster gehostet und ruft einen Schnittstellenzeiger (oder Zeiger) aus dem Steuerelement ab.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|Fügt ein bereits erstelltes Steuerelement an das angegebene Fenster an.|  
|[AtlAxGetHost](#atlaxgethost)|Verwendet, um einen direkten Schnittstellenzeiger zu dem Container für ein bestimmtes Fenster (sofern vorhanden), erhalten anhand des Handles.|  
|[AtlAxGetControl](#atlaxgetcontrol)|Verwendet, um einen direkten Schnittstellenzeiger auf das Steuerelement in einem angegebenen Fenster (sofern vorhanden) enthalten sind, erhalten anhand des Handles.|  
|[AtlSetChildSite](#atlsetchildsite)|Initialisiert die **IUnknown** des untergeordneten Standorts.|  
|[AtlAxWinInit](#atlaxwininit)|Initialisiert den Hostcode für AxWin-Objekte.|  
|[AtlAxWinTerm](#atlaxwinterm)|Hebt die Initialisierung des Hostcodes für AxWin-Objekte.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Gibt Informationen über die standardquellschnittstelle eines Objekts zurück.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlhost.h  

##  <a name="atlaxdialogbox"></a>  AtlAxCreateDialog  
 Erstellt ein modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage.  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 [in] Gibt eine Instanz des Moduls, deren ausführbare Datei der Dialogfeldvorlage enthält.  
  
 `lpTemplateName`  
 [in] Identifiziert die Dialogfeldvorlage. Dieser Parameter ist entweder der Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen des der Dialogfeldvorlage angibt oder ein ganzzahliger Wert, der den Ressourcenbezeichner des der Dialogfeldvorlage angibt. Wenn der Parameter ein Ressourcenbezeichner gibt an, dessen höherwertige Wort muss 0 (null) sein, und seine niederwertige Wort darf des Bezeichners. Sie können die [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) Makro zum Erstellen dieses Werts.  
  
 `hWndParent`  
 [in] Identifiziert das Fenster, das Dialogfeld besitzt.  
  
 `lpDialogProc`  
 [in] Verweist auf die für Standarddialogfelder. Weitere Informationen zu den für Standarddialogfelder, finden Sie unter [DialogProc-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Gibt den Wert zu übergeben, um das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Mit **AtlAxCreateDialog** mit einer Dialogfeldvorlage, die ein ActiveX-Steuerelement enthält, geben Sie einen gültigen **CLSID**, **APPID** oder URL-Zeichenfolge als den *Text* Feld der **Steuerelement** Teil der Dialogfeldressource, zusammen mit "AtlAxWin80" als die *Klassenname* Feld im gleichen Abschnitt. Im folgenden wird veranschaulicht, was eine gültige **Steuerelement** Abschnitt kann folgendermaßen aussehen:  
  
```  
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100  
```  
  
 Weitere Informationen zum Bearbeiten von Ressourcenskripts finden Sie unter [Vorgehensweise: Öffnen einer Ressourcenskriptdatei im Textformat](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Weitere Informationen zu Ressourcendefinition Steueranweisungen, finden Sie unter [allgemeine Steuerelementparameter](http://msdn.microsoft.com/library/windows/desktop/aa380902) unter Windows SDK *: SDK-Tools*.  
  
 Weitere Informationen zu den Dialogfeldern im Allgemeinen, finden Sie unter [Dialogfeld](http://msdn.microsoft.com/library/windows/desktop/ms645452) und [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) im Windows SDK.  
  
##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog  
 Erstellt ein nicht modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage.  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 [in] Gibt eine Instanz des Moduls, deren ausführbare Datei der Dialogfeldvorlage enthält.  
  
 `lpTemplateName`  
 [in] Identifiziert die Dialogfeldvorlage. Dieser Parameter ist entweder der Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen des der Dialogfeldvorlage angibt oder ein ganzzahliger Wert, der den Ressourcenbezeichner des der Dialogfeldvorlage angibt. Wenn der Parameter ein Ressourcenbezeichner gibt an, dessen höherwertige Wort muss 0 (null) sein, und seine niederwertige Wort darf des Bezeichners. Sie können die [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) Makro zum Erstellen dieses Werts.  
  
 `hWndParent`  
 [in] Identifiziert das Fenster, das Dialogfeld besitzt.  
  
 `lpDialogProc`  
 [in] Verweist auf die für Standarddialogfelder. Weitere Informationen zu den für Standarddialogfelder, finden Sie unter [DialogProc-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Gibt den Wert zu übergeben, um das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.  
  
 Finden Sie unter [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) und [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) im Windows SDK.  
  
##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl  
 Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:  
  
-   Eine ProgID z. B. "MSCAL. Calendar.7 "  
  
-   CLSID z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf eine aktive Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment von HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY >\<paarweise >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als ein MSHTML-Stream nicht festgelegt ist.  
  
 `hWnd`  
 [in] Handle für das Fenster, dem an das Steuerelement angefügt wird.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Diese globale Funktion erhalten Sie dieselben Ergebnisse wie beim Aufrufen von [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **, In NULL, NULL, NULL, NULL** );.  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [AtlAxCreateControlLic](#atlaxcreatecontrollic).  
  
##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx  
 Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster. Weiterhin können ein Schnittstellenzeiger und eine Ereignissenke für das neue Steuerelement erstellt werden.  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:  
  
-   Eine ProgID z. B. "MSCAL. Calendar.7 "  
  
-   CLSID z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf eine aktive Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment von HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY >\<paarweise >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als ein MSHTML-Stream nicht festgelegt ist.  
  
 `hWnd`  
 [in] Handle für das Fenster, dem an das Steuerelement angefügt wird.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `ppUnkControl`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des erstellten Steuerelements. Kann **NULL**.  
  
 `iidSink`  
 Der Schnittstellenbezeichner einer ausgehenden Schnittstelle auf die darin enthaltenen Objekte.  
  
 *punkSink*  
 Ein Zeiger auf die **IUnknown** -Schnittstelle des Senkenobjekts Verbindung mit dem Verbindungspunkt gemäß werden `iidSink` enthaltenen Objekts nach den darin enthaltenen Objekte erfolgreich erstellt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 `AtlAxCreateControlEx` ähnelt dem [AtlAxCreateControl](#atlaxcreatecontrol) aber auch können Sie erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement und eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).  
  
##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:  
  
-   Eine ProgID z. B. "MSCAL. Calendar.7 "  
  
-   CLSID z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf eine aktive Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment von HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY >\<paarweise >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als ein MSHTML-Stream nicht festgelegt ist.  
  
 `hWnd`  
 Handle für das Fenster, dem an das Steuerelement angefügt wird.  
  
 `pStream`  
 Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `bstrLic`  
 BSTR, die die Lizenz für das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) ein Beispiel zum Verwenden von `AtlAxCreateControlLic`.  
  
##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx  
 Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster. Weiterhin können ein Schnittstellenzeiger und eine Ereignissenke für das neue Steuerelement erstellt werden.  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert werden:  
  
-   Eine ProgID z. B. "MSCAL. Calendar.7 "  
  
-   CLSID z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf eine aktive Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment von HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY >\<paarweise >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als ein MSHTML-Stream nicht festgelegt ist.  
  
 `hWnd`  
 Handle für das Fenster, dem an das Steuerelement angefügt wird.  
  
 `pStream`  
 Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `ppUnkControl`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des erstellten Steuerelements. Kann **NULL**.  
  
 `iidSink`  
 Der Schnittstellenbezeichner einer ausgehenden Schnittstelle auf die darin enthaltenen Objekte.  
  
 *punkSink*  
 Ein Zeiger auf die **IUnknown** -Schnittstelle des Senkenobjekts Verbindung mit dem Verbindungspunkt gemäß werden `iidSink` enthaltenen Objekts nach den darin enthaltenen Objekte erfolgreich erstellt wurde.  
  
 `bstrLic`  
 BSTR, die die Lizenz für das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 `AtlAxCreateControlLicEx` ähnelt dem [AtlAxCreateControlLic](#atlaxcreatecontrollic) aber auch können Sie erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement und eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) ein Beispiel zum Verwenden von `AtlAxCreateControlLicEx`.  
  
##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl  
 Fügt ein bereits erstelltes Steuerelement an das angegebene Fenster an.  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 [in] Ein Zeiger auf die **IUnknown** des Steuerelements.  
  
 `hWnd`  
 [in] Handle für das Fenster, das das Steuerelement gehostet wird.  
  
 `ppUnkContainer`  
 [out] Ein Zeiger auf einen Zeiger auf die **IUnknown** des Container-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [AtlAxCreateControlEx](#atlaxcreatecontrolex) und [AtlAxCreateControl](#atlaxcreatecontrol) gleichzeitig erstellen und ein Steuerelement anfügen.  
  
> [!NOTE]
>  Das Steuerelementobjekt anzufügende muss ordnungsgemäß initialisiert werden, vor dem Aufruf `AtlAxAttachControl`.  
  
##  <a name="atlaxgethost"></a>  AtlAxGetHost  
 Ruft anhand eines bestimmten Fensters einen direkten Schnittstellenzeiger zu dem Container für das Fenster (sofern vorhanden) ab.  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 [in] Ein Handle für das Fenster, das das Steuerelement gehostet wird.  
  
 `pp`  
 [out] Die **IUnknown** des Containers des Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl  
 Ruft anhand des Handles eines angegebenen Fensters einen direkten Schnittstellenzeiger zu dem Steuerelement ab, das in dem Fenster enthalten ist.  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `h`  
 [in] Ein Handle für das Fenster, das das Steuerelement gehostet wird.  
  
 `pp`  
 [out] Die **IUnknown** des gehosteten Steuerelements.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
##  <a name="atlsetchildsite"></a>  AtlSetChildSite  
 Mit dieser Funktion können Sie die Website eines untergeordneten Objekts zum Festlegen der **IUnknown** des übergeordneten Objekts.  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>Parameter  
 *punkChild*  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des untergeordneten Elements.  
  
 `punkParent`  
 [in] Ein Zeiger auf die **IUnknown** Schnittstelle des übergeordneten Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
##  <a name="atlaxwininit"></a>  AtlAxWinInit  
 Diese Funktion initialisiert den ATL Steuerelements durch Registrierung der **"AtlAxWin80"** und **"AtlAxWinLic80"** Fensterklassen sowie einer Reihe von benutzerdefinierten fenstermeldungen.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung des Steuerelements Hostcode erfolgreich war; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion muss aufgerufen werden, bevor Sie das ATL-Steuerelement, das hosting-API verwenden. Nach einem Aufruf dieser Funktion können die **"AtlAxWin"** Fensterklasse kann verwendet werden, in Aufrufen an [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) oder [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)gemäß der Beschreibung im Windows SDK.  

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm  
 Diese Funktion hebt die Initialisierung ATLs-Steuerelements durch Aufheben der Registrierung der **"AtlAxWin80"** und **"AtlAxWinLic80"** Fensterklassen.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer **"true"**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft einfach [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) wie beschrieben im Windows SDK.  
  
 Mit dieser Funktion wird zum Bereinigen, nachdem alle vorhandenen Hostfenster zerstört wurden, wenn Sie aufgerufen [AtlAxWinInit](#atlaxwininit) und Sie nicht mehr benötigen, Host erstellen. Wenn Sie diese Funktion nicht aufrufen, werden die Fensterklasse aufgehoben automatisch beim Beenden des Prozesses.  
  
##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface  
 Mit dieser Funktion werden Informationen über die Standardquellschnittstelle eines Objekts abgerufen.  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>Parameter  
 `punkObj`  
 [in] Ein Zeiger auf das Objekt, für die Informationen zurückgegeben werden.  
  
 `plibid`  
 [out] Ein Zeiger auf die LIBID der Typbibliothek, die die Definition die Quellschnittstelle enthält.  
  
 `piid`  
 [out] Ein Zeiger auf die Schnittstellen-ID des Objekts Standard-Quellschnittstelle.  
  
 *pdwMajor*  
 [out] Ein Zeiger auf die Hauptversionsnummer der Typbibliothek, die die Definition die Quellschnittstelle enthält.  
  
 *pdwMinor*  
 [out] Ein Zeiger auf die Nebenversionsnummer der Typbibliothek, die die Definition die Quellschnittstelle enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 `AtlGetObjectSourceInterface` können Sie mit der Schnittstellen-ID des Standard-Quellschnittstelle, zusammen mit den LIBID und Haupt- und Nebenversionsnummern der Typbibliothek, die diese Schnittstelle beschreibt bereitstellen.  
  
> [!NOTE]
>  Für diese Funktion, um die angeforderten Informationen erfolgreich abzurufen, das Objekt dargestellte `punkObj` implementieren müssen `IDispatch` (und Zurückgeben von Informationen über **IDispatch:: GetTypeInfo**) plus muss auch Implementieren Sie entweder `IProvideClassInfo2` oder `IPersist`. Die Typinformationen für die Quellschnittstelle muss in der gleichen Typbibliothek als die Typinformationen für `IDispatch`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine Ereignisklasse Senke definieren möglicherweise `CEasySink`, die reduziert der Anzahl der Argumente, die Sie übergeben können `IDispEventImpl` zu bare Essentials. `EasyAdvise` und `EasyUnadvise` verwenden `AtlGetObjectSourceInterface` zum Initialisieren der [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) Elemente vor dem Aufruf [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) oder [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).  
  
 [!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Makros zusammengesetzter Steuerelemente](../../atl/reference/composite-control-macros.md)
