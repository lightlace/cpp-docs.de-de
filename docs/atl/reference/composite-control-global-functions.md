---
title: Globale Funktionen zusammengesetzter Steuerelemente | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: dd043335df32c04349403bbfe38e647f352826c4
ms.lasthandoff: 02/24/2017

---
# <a name="composite-control-global-functions"></a>Globale Funktionen zusammengesetzter Steuerelemente
Diese Funktionen bieten Unterstützung zum Erstellen von Dialogfeldern und zum Erstellen, hosten und Lizenzieren von ActiveX-Steuerelementen.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlAxCreateDialog](#atlaxdialogbox)|Erstellt ein modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage. Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|Erstellt ein nicht modales Dialogfeld aus einer vom Benutzer angegebenen Dialogfeldvorlage. Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|Erstellt ein ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Erstellt ein ActiveX-Steuerelement, initialisiert es, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) des Steuerelements ab.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es und hostet es im angegebenen Fenster.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Erstellt ein lizenziertes ActiveX-Steuerelement, initialisiert es, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger (oder Zeiger) des Steuerelements ab.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|Fügt ein bereits erstelltes Steuerelement an das angegebene Fenster an.|  
|[AtlAxGetHost](#atlaxgethost)|Verwendet, um einen direkten Schnittstellenzeiger zu dem Container für ein bestimmtes Fenster (sofern vorhanden), erhalten anhand des Handles.|  
|[AtlAxGetControl](#atlaxgetcontrol)|Verwendet, um einen direkten Schnittstellenzeiger auf das Steuerelement in einem angegebenen Fenster (sofern vorhanden) enthalten sind, erhalten anhand des Handles.|  
|[AtlSetChildSite](#atlsetchildsite)|Initialisiert die **IUnknown** des untergeordneten Standorts.|  
|[AtlAxWinInit](#atlaxwininit)|Initialisiert den Hostcode für AxWin-Objekte.|  
|[AtlAxWinTerm](#atlaxwinterm)|Hebt die Initialisierung der Hostingcode für AxWin-Objekte.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Gibt Informationen über die standardquellschnittstelle eines Objekts zurück.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlhost.h  

##  <a name="a-nameatlaxdialogboxa--atlaxdialogbox"></a><a name="atlaxdialogbox"></a>AtlAxCreateDialog  
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
 [in] Identifiziert eine Instanz des Moduls, deren ausführbare Datei der Dialogfeldvorlage enthält.  
  
 `lpTemplateName`  
 [in] Identifiziert die Dialogfeldvorlage. Dieser Parameter ist entweder den Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen der Vorlage klicken Sie im Dialogfeld oder ein Integer-Wert, der Ressourcenbezeichner, der die Dialogfeldvorlage angibt. Wenn der Parameter eine Ressourcen-ID angegeben ist, muss seine höherwertige Wort&0; (null) und seine niederwertige Wort muss den Bezeichner enthalten. Sie können die [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) Makro zum Erstellen dieses Werts.  
  
 `hWndParent`  
 [in] Identifiziert das Fenster, das Dialogfeld besitzt.  
  
 `lpDialogProc`  
 [in] Verweist auf die Prozedur. Weitere Informationen zu der Prozedur für Standarddialogfelder, finden Sie unter [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Gibt den Wert der Übergabe an das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden **AtlAxCreateDialog** mit einer Dialogfeldvorlage, die ein ActiveX-Steuerelement enthält, geben Sie eine gültige **CLSID**, **APPID** oder URL-Zeichenfolge als das *Text* Feld der **Steuerelement** Teil die Ressource, zusammen mit "AtlAxWin80" als die *Klassenname* Feld im gleichen Abschnitt. Im folgenden wird veranschaulicht, welche ein gültiger **Steuerelement** Abschnitt könnte folgendermaßen aussehen:  
  
 `CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,`  
  
 `"AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100`  
  
 Weitere Informationen zum Bearbeiten von Ressourcen finden Sie unter [Gewusst wie: Öffnen einer Ressourcenskriptdatei im Textformat](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Weitere Informationen zum Steuerelement Ressourcendefinition Anweisungen, finden Sie unter [allgemeine Parameter](http://msdn.microsoft.com/library/windows/desktop/aa380902) unter [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *: SDK-Tools*.  
  
 Weitere Informationen über Dialogfelder im Allgemeinen finden Sie unter [Dialogfeld](http://msdn.microsoft.com/library/windows/desktop/ms645452) und [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameatlaxcreatedialoga--atlaxcreatedialog"></a><a name="atlaxcreatedialog"></a>AtlAxCreateDialog  
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
 [in] Identifiziert eine Instanz des Moduls, deren ausführbare Datei der Dialogfeldvorlage enthält.  
  
 `lpTemplateName`  
 [in] Identifiziert die Dialogfeldvorlage. Dieser Parameter ist entweder den Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen der Vorlage klicken Sie im Dialogfeld oder ein Integer-Wert, der Ressourcenbezeichner, der die Dialogfeldvorlage angibt. Wenn der Parameter eine Ressourcen-ID angegeben ist, muss seine höherwertige Wort&0; (null) und seine niederwertige Wort muss den Bezeichner enthalten. Sie können die [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) Makro zum Erstellen dieses Werts.  
  
 `hWndParent`  
 [in] Identifiziert das Fenster, das Dialogfeld besitzt.  
  
 `lpDialogProc`  
 [in] Verweist auf die Prozedur. Weitere Informationen zu der Prozedur für Standarddialogfelder, finden Sie unter [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Gibt den Wert der Übergabe an das Dialogfeld in der **lParam** Parameter von der **WM_INITDIALOG** Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Im daraufhin angezeigten Dialogfeld kann ActiveX-Steuerelemente enthalten.  
  
 Finden Sie unter [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) und [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameatlaxcreatecontrola--atlaxcreatecontrol"></a><a name="atlaxcreatecontrol"></a>AtlAxCreateControl  
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
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert sein:  
  
-   Eine ProgID, z. B. "MSCAL. Calendar.7 "  
  
-   Der CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment der HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als eine MSHTML-Stream festgelegt ist.  
  
 `hWnd`  
 [in] Handle für das Fenster, dem das Steuerelement angehängt werden.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Diese globale Funktion erhalten Sie dieselben Ergebnisse wie beim Aufruf von [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **NULL, NULL, NULL, NULL** );.  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [AtlAxCreateControlLic](#atlaxcreatecontrollic).  
  
##  <a name="a-nameatlaxcreatecontrolexa--atlaxcreatecontrolex"></a><a name="atlaxcreatecontrolex"></a>AtlAxCreateControlEx  
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
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert sein:  
  
-   Eine ProgID, z. B. "MSCAL. Calendar.7 "  
  
-   Der CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment der HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als eine MSHTML-Stream festgelegt ist.  
  
 `hWnd`  
 [in] Handle für das Fenster, dem das Steuerelement angehängt werden.  
  
 `pStream`  
 [in] Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `ppUnkControl`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Steuerelements erstellt. Kann **NULL**.  
  
 `iidSink`  
 Der Schnittstellenbezeichner des Ausgangsschnittstelle enthaltenen Objekts.  
  
 *punkSink*  
 Ein Zeiger auf die **IUnknown** -Schnittstelle des Senkenobjekts mit dem angegebenen Verbindungspunkt verbunden sein, `iidSink` enthaltenen Objekts, nachdem das enthaltene Objekt erfolgreich erstellt wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 `AtlAxCreateControlEx`ähnelt dem [AtlAxCreateControl](#atlaxcreatecontrol) aber darüber hinaus können Sie erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement und eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
 Um ein lizenziertes ActiveX-Steuerelement zu erstellen, finden Sie unter [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).  
  
##  <a name="a-nameatlaxcreatecontrollica--atlaxcreatecontrollic"></a><a name="atlaxcreatecontrollic"></a>AtlAxCreateControlLic  
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
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert sein:  
  
-   Eine ProgID, z. B. "MSCAL. Calendar.7 "  
  
-   Der CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment der HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als eine MSHTML-Stream festgelegt ist.  
  
 `hWnd`  
 Handle für das Fenster, dem das Steuerelement angehängt werden.  
  
 `pStream`  
 Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `bstrLic`  
 BSTR, die Lizenz für das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) ein Beispiel zum Verwenden von `AtlAxCreateControlLic`.  
  
##  <a name="a-nameatlaxcreatecontrollicexa--atlaxcreatecontrollicex"></a><a name="atlaxcreatecontrollicex"></a>AtlAxCreateControlLicEx  
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
 Ein Zeiger auf eine Zeichenfolge, die an das Steuerelement übergeben werden. Muss in einem der folgenden Arten formatiert sein:  
  
-   Eine ProgID, z. B. "MSCAL. Calendar.7 "  
  
-   Der CLSID wie z. B. "{8E27C92B-1264-101C-8A2F-040224009C02}"  
  
-   Eine URL wie "http://www.microsoft.com"  
  
-   Ein Verweis auf ein aktives Dokument wie "file://\\\Documents\MyDoc.doc"  
  
-   Ein Fragment der HTML, wie z. B. "MSHTML:\<HTML >\<Text > Dies ist eine Textzeile\</BODY > \< /HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" muss vor der HTML-Fragment ausgeführt werden, damit es als eine MSHTML-Stream festgelegt ist.  
  
 `hWnd`  
 Handle für das Fenster, dem das Steuerelement angehängt werden.  
  
 `pStream`  
 Ein Zeiger auf einen Stream, der zum Initialisieren der Eigenschaften des Steuerelements verwendet wird. Kann **NULL**.  
  
 `ppUnkContainer`  
 Die Adresse eines Zeigers, die erhalten die **IUnknown** des Containers. Kann **NULL**.  
  
 `ppUnkControl`  
 [out] Die Adresse eines Zeigers, die erhalten die **IUnknown** des Steuerelements erstellt. Kann **NULL**.  
  
 `iidSink`  
 Der Schnittstellenbezeichner des Ausgangsschnittstelle enthaltenen Objekts.  
  
 *punkSink*  
 Ein Zeiger auf die **IUnknown** -Schnittstelle des Senkenobjekts mit dem angegebenen Verbindungspunkt verbunden sein, `iidSink` enthaltenen Objekts, nachdem das enthaltene Objekt erfolgreich erstellt wurde.  
  
 `bstrLic`  
 BSTR, die Lizenz für das Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 `AtlAxCreateControlLicEx`ähnelt dem [AtlAxCreateControlLic](#atlaxcreatecontrollic) aber darüber hinaus können Sie erhalten einen Schnittstellenzeiger auf das neu erstellte Steuerelement und eine Ereignissenke zum Empfangen von Ereignissen, die vom Steuerelement ausgelöst.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [Hosten von ActiveX-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) ein Beispiel zum Verwenden von `AtlAxCreateControlLicEx`.  
  
##  <a name="a-nameatlaxattachcontrola--atlaxattachcontrol"></a><a name="atlaxattachcontrol"></a>AtlAxAttachControl  
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
 [in] Handle für das Fenster, das das Steuerelement hostet.  
  
 `ppUnkContainer`  
 [out] Ein Zeiger auf einen Zeiger auf die **IUnknown** des Containerobjekts.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der HRESULT-Standardwerte.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [AtlAxCreateControlEx](#atlaxcreatecontrolex) und [AtlAxCreateControl](#atlaxcreatecontrol) zu erstellen und gleichzeitig ein Steuerelement anfügen.  
  
> [!NOTE]
>  Das Steuerelementobjekt anzufügende muss korrekt initialisiert werden, vor dem Aufruf von `AtlAxAttachControl`.  
  
##  <a name="a-nameatlaxgethosta--atlaxgethost"></a><a name="atlaxgethost"></a>AtlAxGetHost  
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
 Einer der HRESULT-Standardwerte.  
  
##  <a name="a-nameatlaxgetcontrola--atlaxgetcontrol"></a><a name="atlaxgetcontrol"></a>AtlAxGetControl  
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
 Einer der HRESULT-Standardwerte.  
  
##  <a name="a-nameatlsetchildsitea--atlsetchildsite"></a><a name="atlsetchildsite"></a>AtlSetChildSite  
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
  
##  <a name="a-nameatlaxwininita--atlaxwininit"></a><a name="atlaxwininit"></a>AtlAxWinInit  
 Diese Funktion initialisiert den ATL Steuerelement hosten von Code durch die Registrierung der **"AtlAxWin80"** und **"AtlAxWinLic80"** Fensterklassen sowie einer Reihe von benutzerdefinierten fenstermeldungen.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Initialisierung des Steuerelements Hostingcode erfolgreich war; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion muss aufgerufen werden, bevor Sie das ATL-Steuerelement-hosting-API verwenden. Nach einem Aufruf dieser Funktion die **"AtlAxWin"** Fensterklasse kann verwendet werden, Aufrufe [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) oder [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  

##  <a name="a-nameatlaxwinterma--atlaxwinterm"></a><a name="atlaxwinterm"></a>AtlAxWinTerm  
 Diese Funktion hebt die Initialisierung ATLs-Steuerelement hosten von Code durch das Aufheben der Registrierung der **"AtlAxWin80"** und **"AtlAxWinLic80"** -Klassen.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer **TRUE**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft einfach [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Rufen Sie diese Funktion bereinigen, nachdem alle vorhandenen Hostfenster zerstört wurden, wenn Sie aufgerufen [AtlAxWinInit](#atlaxwininit) und müssen nicht mehr Hostfenster zu erstellen. Wenn Sie diese Funktion nicht aufrufen, werden die Fensterklasse aufgehoben automatisch bei Beendigung des Prozesses.  
  
##  <a name="a-nameatlgetobjectsourceinterfacea--atlgetobjectsourceinterface"></a><a name="atlgetobjectsourceinterface"></a>AtlGetObjectSourceInterface  
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
 [in] Ein Zeiger auf das Objekt, für den Informationen zurückgegeben werden.  
  
 `plibid`  
 [out] Ein Zeiger auf die LIBID der Typbibliothek, die die Definition der Quellschnittstelle.  
  
 `piid`  
 [out] Ein Zeiger auf die Schnittstellen-ID des Objekts Standard-Quellschnittstelle.  
  
 *pdwMajor*  
 [out] Ein Zeiger auf die Hauptversionsnummer der Typbibliothek, die die Definition der Quellschnittstelle.  
  
 *pdwMinor*  
 [out] Ein Zeiger auf die Nebenversionsnummer der Typbibliothek, die die Definition der Quellschnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 `AtlGetObjectSourceInterface`können Sie mit der Schnittstellen-ID der Quelle Standardschnittstelle, zusammen mit der LIBID und umfangreichen und Nebenversionsnummern der Typbibliothek, die diese Schnittstelle beschreibt bereitstellen.  
  
> [!NOTE]
>  Für diese Funktion die angeforderte Informationen empfangen, das Objekt dargestellte `punkObj` müssen implementieren `IDispatch` (und Zurückgeben von Informationen über **IDispatch:: GetTypeInfo**) plus auch implementieren entweder `IProvideClassInfo2` oder `IPersist`. Die Typinformationen für die Quellschnittstelle muss sich in derselben Typbibliothek als Informationen für den `IDispatch`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine Ereignisklasse Senke definieren möglicherweise `CEasySink`, reduzieren die Anzahl der Argumente, die an übergeben können `IDispEventImpl` zu den absolut erforderlichen Funktionen. `EasyAdvise`und `EasyUnadvise` verwenden `AtlGetObjectSourceInterface` zum Initialisieren der [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) Elemente vor dem Aufruf von [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) oder [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).  
  
 [!code-cpp[NVC_ATL_Windowing&#93;](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Makros zusammengesetzter Steuerelemente](../../atl/reference/composite-control-macros.md)

