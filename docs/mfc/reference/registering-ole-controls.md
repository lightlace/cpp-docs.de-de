---
title: Registrieren von OLE-Steuerelemente | Microsoft-Dokumentation
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
ms.openlocfilehash: 4855ca5c461b7437345150f5d199521c48f0b253
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196552"
---
# <a name="registering-ole-controls"></a>Registrieren des OLE-Steuerelements
OLE-Steuerelemente, wie andere OLE-Server-Objekte, können von anderen OLE-fähige Anwendungen zugegriffen werden. Dies erfolgt durch die Registrierung der Typbibliothek und der Klasse des Steuerelements.  
  
 Die folgenden Funktionen können Sie zum Hinzufügen und Entfernen des Steuerelements-Klasse, Eigenschaftenseiten und Typbibliothek in der Datenbank der Windows-Registrierung:  
  
### <a name="registering-ole-controls"></a>Registrieren des OLE-Steuerelements  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Fügt der Klasse des Steuerelements in der Registrierungsdatenbank.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Eine Eigenschaftenseite des Steuerelements und der Registrierungsdatenbank hinzugefügt.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Typbibliothek des Steuerelements und der Registrierungsdatenbank hinzugefügt.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Entfernt eine Steuerelementklasse oder eine Eigenschaftenseitenklasse aus der Registrierungsdatenbank an.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Wird die Typbibliothek des Steuerelements aus der Registrierungsdatenbank entfernt.|  
  
 `AfxOleRegisterTypeLib` in der Implementierung von DLL-Steuerelement in der Regel heißt `DllRegisterServer`. Auf ähnliche Weise `AfxOleUnregisterTypeLib` wird aufgerufen, indem `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, und `AfxOleUnregisterClass` in der Regel von aufgerufen werden, die `UpdateRegistry` Memberfunktion Seitenrand eines Steuerelements Klasse Vorinstallations- oder -Eigenschaft.  
  
##  <a name="afxoleregistercontrolclass"></a>  AfxOleRegisterControlClass  
 Registriert die Control-Klasse mit der Datenbank der Windows-Registrierung.  
  
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
 *hInstance*  
 Der Instanzhandle des Moduls im Zusammenhang mit der Control-Klasse.  
  
 *clsid*  
 Die eindeutige Klasse-ID des Steuerelements.  
  
 *pszProgID*  
 Die eindeutige Programm-ID des Steuerelements.  
  
 *idTypeName*  
 Die Ressourcen-ID der Zeichenfolge, die einen Benutzer lesbaren Namen für das Steuerelement enthält.  
  
 *idBitmap*  
 Die Ressourcen-ID der Bitmap für die Darstellung des OLE-Steuerelements in einer Symbolleiste oder die Palette verwendet werden soll.  
  
 *nRegFlags*  
 Enthält eine oder mehrere der folgenden Flags:  
  
- `afxRegInsertable` Ermöglicht das Steuerelement im Dialogfeld "Objekt einfügen" für OLE-Objekte angezeigt.  
  
- `afxRegApartmentThreading` Legt das threading-Modell in der Registrierung ThreadingModel = Apartment.  
  
- `afxRegFreeThreading` Legt das threading-Modell in der Registrierung ThreadingModel = frei.  
  
     Sie können die beiden Flags kombinieren `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = Both. Finden Sie unter [InprocServer32](/windows/desktop/com/inprocserver32) im Windows SDK für Weitere Informationen zum threading modellregistrierung.  
  
> [!NOTE]
>  In MFC-Versionen vor MFC 4.2 die **Int** *nRegFlags* Parameter wurde ein Parameter "bool" *bInsertable*, die zulässige bzw. nicht Sie das Steuerelement, aus dem Einfügevorgang eingefügt werden soll Dialogfeld "Objekt".  
  
 *dwMiscStatus*  
 Enthält eine oder mehrere der folgenden Statusflags (für eine Beschreibung der Flags für OLEMISC-Enumeration finden Sie im Windows SDK):  
  
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
 Die eindeutige ID der Steuerelement-Klasse.  
  
 *wVerMajor*  
 Die Hauptversionsnummer der Steuerelement-Klasse.  
  
 *wVerMinor*  
 Die Nebenversionsnummer der Steuerelement-Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Control-Klasse registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird das Steuerelement von Containern verwendet werden, die OLE-Control-bewusst sind. `AfxOleRegisterControlClass` aktualisiert die Registrierung mit dem Namen und Speicherort auf dem System des Steuerelements, und legt auch fest, das threading-Modell, das das Steuerelement in der Registrierung unterstützt. Weitere Informationen finden Sie unter [technischen Hinweis 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartment-Modell Threading in OLE-Steuerelemente," und [zu Prozessen und Threads](/windows/desktop/ProcThread/about-processes-and-threads) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl#11](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 Im obige Beispiel wird veranschaulicht, wie `AfxOleRegisterControlClass` mit dem Flag für einfügbar aufgerufen wird und das Flag für Apartment-Modell ORed zusammengeführt, um der sechste Parameter zu erstellen:  
  
 [!code-cpp[NVC_MFCAxCtl#12](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Das Steuerelement wird in das Dialogfeld "Objekt einfügen" für aktivierte Container angezeigt, und Apartment modellfähige werden. Modellfähige Apartment-Steuerelemente müssen statische Klasse, die Daten durch Sperren geschützt ist, so, dass während ein Steuerelements in einem Apartment die statischen Daten zugreift, sie ist nicht vom Scheduler deaktiviert bevor abgeschlossen ist, und eine andere Instanz derselben Klasse beginnt mit die gleichen statischen Daten. Alle Zugriffe auf die statischen Daten werden von kritischen Abschnittscode eingeschlossen werden.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>  AfxOleRegisterPropertyPageClass  
 Registriert die Eigenschaftenseitenklasse mit der Datenbank der Windows-Registrierung.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Parameter  
 *hInstance*  
 Der Instanzhandle des Moduls Eigenschaftenseitenklasse zugeordnet werden soll.  
  
 *clsid*  
 Die eindeutige Klasse-ID der Eigenschaftenseite.  
  
 *idTypeName*  
 Die Ressourcen-ID der Zeichenfolge, die einen Benutzer lesbarer Name für die Eigenschaftenseite enthält.  
  
 *nRegFlags*  
 Kann das Flag enthalten:  
  
- `afxRegApartmentThreading` Legt das threading-Modell in der Registrierung ThreadingModel = Apartment.  
  
> [!NOTE]
>  In den MFC-Versionen vor MFC 4.2 ermöglichen die **Int** *nRegFlags* Parameter war nicht verfügbar. Beachten Sie auch, dass die `afxRegInsertable` Flag ist keine gültige Option für die Eigenschaftenseiten und führt dazu, dass eine Bestätigung in MFC ist die Eigenschaft festgelegt  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Control-Klasse registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird die Eigenschaftenseite von Containern verwendet werden, die OLE-Control-bewusst sind. `AfxOleRegisterPropertyPageClass` aktualisiert die Registrierung mit dem Namen der Seite und den Speicherort auf dem System, und legt auch fest, das threading-Modell, das das Steuerelement in der Registrierung unterstützt. Weitere Informationen finden Sie unter [technischen Hinweis 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartment-Modell Threading in OLE-Steuerelemente," und [zu Prozessen und Threads](/windows/desktop/ProcThread/about-processes-and-threads) im Windows SDK.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>  AfxOleRegisterTypeLib  
 Die Typbibliothek registriert, mit der Windows-Registrierung-Datenbank und ermöglicht die Typbibliothek, die von anderen Containern verwendet werden, die OLE-Control-bewusst sind.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 *hInstance*  
 Der Instanzhandle, der die Anwendung, die der Typbibliothek zugeordnet werden soll.  
  
 *tlid*  
 Die eindeutige ID der Typbibliothek.  
  
 *pszFileName*  
 Der optionale Dateiname einer lokalisierten Typbibliothek verweist (. TLB)-Datei für das Steuerelement.  
  
 *pszHelpDir*  
 Der Name des Verzeichnisses, in die Hilfedatei für die Typbibliothek gefunden werden kann. Wenn NULL, wird angenommen, dass die Datei im gleichen Verzeichnis wie die Typbibliothek selbst werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Typbibliothek registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird die Registrierung mit den Namen der Typbibliothek und den Speicherort auf dem System aktualisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation#7](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#8](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>  AfxOleUnregisterClass  
 Entfernt den Steuerelements oder einer Eigenschaft Klasse seiteneintrag aus der Datenbank der Windows-Registrierung.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Parameter  
 *clsID*  
 Die eindeutige Klasse-ID des Steuerelements oder der Eigenschaft.  
  
 *pszProgID*  
 Die eindeutige Programm-ID des Steuerelements oder der Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Seitenklasse Steuerelements oder einer Eigenschaft erfolgreich aufgehoben wurde; andernfalls 0.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>  AfxOleUnregisterTypeLib  
 Rufen Sie diese Funktion, um den Typ-Bibliothek-Eintrag aus der Datenbank der Windows-Registrierung zu entfernen.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Parameter  
 *tlID*  
 Die eindeutige ID der Typbibliothek.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Bibliothek erfolgreich aufgehoben wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl#13](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
