---
title: Registrieren von OLE-Steuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls [MFC], registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e51e4c425d3d16b57a2b1ce0d4fc2f585dc505d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378056"
---
# <a name="registering-ole-controls"></a>Registrieren des OLE-Steuerelements
OLE-Steuerelemente, wie andere OLE-Server-Objekte können von anderen OLE-fähigen Anwendungen zugegriffen werden. Dies erfolgt durch die Registrierung der Typbibliothek und der Klasse des Steuerelements.  
  
 Die folgenden Funktionen ermöglicht Ihnen das Hinzufügen und entfernen die Control-Klasse, Eigenschaftenseiten und Typbibliothek in der Datenbank der Windows-Registrierung:  
  
### <a name="registering-ole-controls"></a>Registrieren des OLE-Steuerelements  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Die Registrierungsdatenbank hinzugefügt der Klasse des Steuerelements.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Die Registrierungsdatenbank hinzugefügt eine Eigenschaftenseite Steuerelement.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Das Steuerelement-Typbibliothek und der Registrierungsdatenbank hinzugefügt.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Entfernt eine Steuerelementklasse oder eine Eigenschaft Seite aus der Registrierungsdatenbank.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Entfernt das Steuerelement-Typbibliothek aus der Registrierungsdatenbank.|  
  
 `AfxOleRegisterTypeLib` heißt in der Regel in einem Steuerelement-DLL-Implementierung von `DllRegisterServer`. Auf ähnliche Weise `AfxOleUnregisterTypeLib` wird aufgerufen, indem Sie `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, und `AfxOleUnregisterClass` heißen in der Regel durch die `UpdateRegistry` Memberfunktion eines Steuerelements Klasse Factory oder Eigenschaftenseite.  
  
##  <a name="afxoleregistercontrolclass"></a>  AfxOleRegisterControlClass  
 Registriert die Steuerelementklasse mit der Windows-Registrierung-Datenbank.  
  
```   
BOOL AFXAPI AfxOleRegisterControlClass(
    HINSTANCE hInstance,  
    REFCLSID clsid,  
    LPCTSTR pszProgID,  
    UINT idTypeName,  
    UINT idBitmap,  
    int nRegFlags,  
    DWORD dwMiscStatus,  
    REFGUID tlid,  
    WORD wVerMajor,  
    WORD wVerMinor); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle, von dem Modul mit der Control-Klasse zugeordnet werden soll.  
  
 `clsid`  
 Die eindeutige Klassen-ID des Steuerelements.  
  
 `pszProgID`  
 Die eindeutige Programm-ID des Steuerelements.  
  
 `idTypeName`  
 Die Ressourcen-ID der Zeichenfolge, die einen Benutzer lesbaren Namen für das Steuerelement enthält.  
  
 *idBitmap*  
 Die Ressourcen-ID der Bitmap für die Darstellung des OLE-Steuerelements in einer Symbolleiste oder Palette verwendet werden soll.  
  
 `nRegFlags`  
 Enthält eine oder mehrere der folgenden Flags:  
  
- `afxRegInsertable` Ermöglicht das Steuerelement im Dialogfeld "Objekt einfügen" für OLE-Objekte angezeigt.  
  
- `afxRegApartmentThreading` Legt das Threadingmodell in der Registrierung auf ThreadingModel = Apartment.  
  
- `afxRegFreeThreading` Legt das Threadingmodell in der Registrierung auf ThreadingModel = frei.  
  
     Sie können die zwei Flags kombinieren `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = Both. Finden Sie unter [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) in das Windows SDK für Weitere Informationen zum Modell Registrierung threading.  
  
> [!NOTE]
>  In MFC-Versionen vor MFC 4.2 die `int` `nRegFlags` Parameter wurde ein **BOOL** Parameter *bInsertable*, die zulässige oder unzulässige das Steuerelement, das aus das Dialogfeld "Objekt einfügen" eingefügt werden Box.  
  
 *dwMiscStatus*  
 Enthält eine oder mehrere der folgenden Statusflags (eine Beschreibung der Flags finden Sie in **OLEMISC** Enumeration im Windows SDK):  
  
-   OLEMISC_RECOMPOSEONRESIZE  
  
-   OLEMISC_ONLYICONIC  
  
-   OLEMISC_INSERTNOTREPLACE  
  
-   OLEMISC_STATIC  
  
-   OLEMISC_CANTLINKINSIDE  
  
-   OLEMISC_CANLINKBYOLE1  
  
-   OLEMISC_ISLINKOBJECT  
  
-   OLEMISC_INSIDEOUT  
  
-   OLEMISC_ACTIVATEWHENVISIBLE  
  
-   OLEMISC_RENDERINGISDEVICEINDEPENDENT  
  
-   OLEMISC_INVISIBLEATRUNTIME  
  
-   OLEMISC_ALWAYSRUN  
  
-   OLEMISC_ACTSLIKEBUTTON  
  
-   OLEMISC_ACTSLIKELABEL  
  
-   OLEMISC_NOUIACTIVATE  
  
-   OLEMISC_ALIGNABLE  
  
-   OLEMISC_IMEMODE  
  
-   OLEMISC_SIMPLEFRAME  
  
-   OLEMISC_SETCLIENTSITEFIRST  
  
 *tlid*  
 Die eindeutige ID von der Control-Klasse.  
  
 `wVerMajor`  
 Die Hauptversionsnummer der Control-Klasse.  
  
 `wVerMinor`  
 Die Nebenversionsnummer der Control-Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Steuerelementklasse registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird das Steuerelement von Containern verwendet werden, die OLE-Control-fähig sind. `AfxOleRegisterControlClass` ein Update der Registrierung mit Namen und den Speicherort auf dem System des Steuerelements, und zudem das Threadingmodell an, dem das Steuerelement in der Registrierung unterstützt wird. Weitere Informationen finden Sie unter [technischen Hinweis 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartmentmodell Threading in OLE-Steuerelemente," und [zu Prozessen und Threads](http://msdn.microsoft.com/library/windows/desktop/ms681917) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 Im obigen Beispiel wird veranschaulicht, wie `AfxOleRegisterControlClass` mit dem Flag für einfügbar aufgerufen wird und das Flag für Apartment modellieren ORed zusammen, um die sechste Parameter zu erstellen:  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Das Steuerelement wird im Dialogfeld "Objekt einfügen" für aktivierte Container angezeigt, und die Apartment modellfähige werden. Apartment modellfähige Steuerelemente müssen statische Klasse, die Daten durch Sperren geschützt werden Stellen Sie sicher, sodass während ein Steuerelements in einem Apartment die statischen Daten zugreift, er ist nicht vom Planer deaktiviert, bevor er abgeschlossen ist, und mit einer anderen Instanz derselben Klasse gestartet wird die gleichen statischen Daten. Alle Zugriffe auf die statische Daten werden kritische Abschnittscode eingeschlossen werden.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass  
 Registriert die Eigenschaft Page-Klasse mit der Windows-Registrierung-Datenbank.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle des Moduls die Eigenschaftenseitenklasse zugeordnet werden soll.  
  
 `clsid`  
 Die eindeutige Klassen-ID der Eigenschaftenseite.  
  
 `idTypeName`  
 Die Ressourcen-ID der Zeichenfolge, die einen Benutzer lesbaren Namen für die Eigenschaftsseite "enthält.  
  
 `nRegFlags`  
 Das Flag kann Elemente enthalten:  
  
- `afxRegApartmentThreading` Legt das Threadingmodell in der Registrierung auf ThreadingModel = Apartment.  
  
> [!NOTE]
>  In den MFC-Versionen vor MFC 4.2 die `int` `nRegFlags` Parameter war nicht verfügbar. Beachten Sie auch, dass die `afxRegInsertable` Flag ist keine gültige Option für Eigenschaftenseiten und führt dazu, dass eine ASSERTION in MFC ist die Eigenschaft festgelegt  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Steuerelementklasse registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird die Eigenschaftenseite von Containern verwendet werden, die OLE-Control-fähig sind. `AfxOleRegisterPropertyPageClass` ein Update der Registrierung mit den Namen der Seite und den Speicherort auf dem System, und zudem das Threadingmodell an, dem das Steuerelement in der Registrierung unterstützt wird. Weitere Informationen finden Sie unter [technischen Hinweis 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartmentmodell Threading in OLE-Steuerelemente," und [zu Prozessen und Threads](http://msdn.microsoft.com/library/windows/desktop/ms681917) im Windows SDK.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib  
 Die Typbibliothek mit der Windows-Registrierungsdatenbank registriert, und ermöglicht die Typbibliothek, die von anderen Containern verwendet werden, die OLE-Control-fähig sind.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle, der die Anwendung mit der Typbibliothek.  
  
 *tlid*  
 Die eindeutige ID der Typbibliothek.  
  
 *pszFileName*  
 Verweist auf den optionalen Dateinamen einer lokalisierten Typbibliothek (. TLB)-Datei für das Steuerelement.  
  
 *pszHelpDir*  
 Der Name des Verzeichnisses, in dem die Hilfedatei für die Typbibliothek gefunden werden kann. Wenn **NULL**, wird angenommen, dass die Hilfedatei im selben Verzeichnis wie die Typbibliothek selbst sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Typbibliothek registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert die Registrierung mit dem Namen der Typbibliothek und deren Position auf dem System.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass  
 Entfernt den Eintrag Steuerelement oder eine Eigenschaft Seite Klasse aus der Datenbank der Windows-Registrierung.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Parameter  
 *clsID*  
 Die eindeutige Klassen-ID des Steuerelements oder der Eigenschaft.  
  
 `pszProgID`  
 Die eindeutige Programm-ID des Steuerelements oder der Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Steuerelement oder eine Eigenschaft Page-Klasse wurde erfolgreich aufgehoben wurde; andernfalls 0.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib  
 Rufen Sie diese Funktion, um den Typ Bibliothekseintrag aus der Datenbank der Windows-Registrierung zu entfernen.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Parameter  
 `tlID`  
 Die eindeutige ID der Typbibliothek.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Typbibliothek erfolgreich aufgehoben wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
