---
title: Registrieren von OLE-Steuerelementen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- registering OLE controls
- OLE controls, registering
ms.assetid: 73c45b7f-7dbc-43f5-bd17-dd77c6acec72
caps.latest.revision: 15
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9c54fb7dc3802e78c8dc68df02ff55ef4732a36b
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="registering-ole-controls"></a>Registrieren des OLE-Steuerelements
OLE-Steuerelemente, wie andere OLE-Server-Objekte können von anderen OLE-kompatible Anwendung zugegriffen werden. Dies erfolgt durch die Registrierung der Typbibliothek und der Klasse des Steuerelements.  
  
 Die folgenden Funktionen können Sie zum Hinzufügen und Entfernen des Steuerelements Klasse, Eigenschaftenseiten und Typbibliothek in der Datenbank der Windows-Registrierung:  
  
### <a name="registering-ole-controls"></a>Registrieren des OLE-Steuerelements  
  
|||  
|-|-|  
|[AfxOleRegisterControlClass](#afxoleregistercontrolclass)|Fügt der Klasse des Steuerelements in der Registrierungsdatenbank.|  
|[AfxOleRegisterPropertyPageClass](#afxoleregisterpropertypageclass)|Die Registrierungsdatenbank hinzugefügt eine-Steuerelement Eigenschaftenseite.|  
|[AfxOleRegisterTypeLib](#afxoleregistertypelib)|Die Registrierungsdatenbank hinzugefügt Typbibliothek des Steuerelements.|  
|[AfxOleUnregisterClass](#afxoleunregisterclass)|Entfernt eine Steuerelement-Klasse oder eine Eigenschaft Page-Klasse in der Registrierungsdatenbank.|  
|[AfxOleUnregisterTypeLib](#afxoleunregistertypelib)|Entfernt das Steuerelement-Typbibliothek in der Registrierungsdatenbank.|  
  
 `AfxOleRegisterTypeLib`wird normalerweise aufgerufen, in einem Steuerelement-DLL-Implementierung von `DllRegisterServer`. Auf ähnliche Weise `AfxOleUnregisterTypeLib` wird aufgerufen, indem Sie `DllUnregisterServer`. `AfxOleRegisterControlClass`, `AfxOleRegisterPropertyPageClass`, und `AfxOleUnregisterClass` sind in der Regel aufgerufen, durch die `UpdateRegistry` -Memberfunktion des eines Steuerelements Klasse Factory oder der Eigenschaft.  
  
##  <a name="afxoleregistercontrolclass"></a>AfxOleRegisterControlClass  
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
 `hInstance`  
 Der Instanzhandle des Moduls im Zusammenhang mit der Control-Klasse.  
  
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
  
- `afxRegInsertable`Ermöglicht das Steuerelement im Dialogfeld "Objekt einfügen" für OLE-Objekte angezeigt werden.  
  
- `afxRegApartmentThreading`Legt das Threadingmodell in der Registrierung ThreadingModel = Apartment.  
  
- `afxRegFreeThreading`Legt das Threadingmodell in der Registrierung ThreadingModel = frei.  
  
     Die zwei Flags können kombiniert werden `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = beides. Finden Sie unter [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen über threading-Modell-Registrierung.  
  
> [!NOTE]
>  In MFC-Versionen vor MFC 4.2 die `int` `nRegFlags` Parameter war ein **BOOL** Parameter *bInsertable*, die zulässige oder unzulässige des Steuerelements im Dialogfeld "Objekt einfügen" eingefügt werden.  
  
 *dwMiscStatus*  
 Enthält eine oder mehrere der folgenden Statusflags (eine Beschreibung der Flags finden Sie unter **OLEMISC** -Enumeration in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]):  
  
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
 Die eindeutige ID der Control-Klasse.  
  
 `wVerMajor`  
 Die Hauptversionsnummer der Control-Klasse.  
  
 `wVerMinor`  
 Die Nebenversionsnummer der Control-Klasse.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Control-Klasse registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird das Steuerelement von Containern verwendet werden, die OLE-Steuerelements bekannt sind. `AfxOleRegisterControlClass`aktualisiert die Registrierung mit dem Namen und den Speicherort auf dem System des Steuerelements und das threading-Modell, das das Steuerelement in der Registrierung unterstützt wird. Weitere Informationen finden Sie unter [Technische Hinweis 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartmentmodell Threading in OLE-Steuerelemente," und [zu Prozessen und Threads](http://msdn.microsoft.com/library/windows/desktop/ms681917) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl&#11;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_1.cpp)]  
  
 Im obigen Beispiel wird veranschaulicht, wie `AfxOleRegisterControlClass` mit dem Flag für einfügbar aufgerufen wird und die Kennzeichen für Apartment-Modell or zusammengeführt, um der sechste Parameter zu erstellen:  
  
 [!code-cpp[NVC_MFCAxCtl&#12;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_2.cpp)]  
  
 Das Steuerelement wird im Dialogfeld Objekt einfügen für aktivierte Container angezeigt, und die Apartment-Modell unterstützt werden. Apartment-Modell-fähigen Steuerelemente müssen statische Klasse, die Daten durch Sperren geschützt werden, damit während ein Steuerelements in einem Apartment die statischen Daten zugreift, es nicht vom Planer deaktiviert vor abgeschlossen ist, und eine andere Instanz der Klasse verwenden die gleichen statischen Daten. Kritischen Abschnittscode werden alle Zugriffe auf die statischen Daten eingeschlossen werden.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleregisterpropertypageclass"></a>AfxOleRegisterPropertyPageClass  
 Registriert die Eigenschaftenseitenklasse mit der Datenbank der Windows-Registrierung.  
  
```  
BOOL AFXAPI AfxOleRegisterPropertyPageClass(
   HINSTANCE hInstance,  
   REFCLSID  clsid,  
   UINT idTypeName,  
   int nRegFlags); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle des Moduls der Eigenschaft Page-Klasse zugeordnet.  
  
 `clsid`  
 Die eindeutige Klassen-ID der Eigenschaftenseite.  
  
 `idTypeName`  
 Die Ressourcen-ID der Zeichenfolge, die ein Benutzer lesbare Name für die Eigenschaftenseite enthält.  
  
 `nRegFlags`  
 Das Flag kann Elemente enthalten:  
  
- `afxRegApartmentThreading`Legt das Threadingmodell in der Registrierung ThreadingModel = Apartment.  
  
> [!NOTE]
>  In MFC, Version 4.2 MFC die `int` `nRegFlags` Parameter war nicht verfügbar. Beachten Sie auch, dass die `afxRegInsertable` -Flag ist keine gültige Option für Eigenschaftenseiten und eine Bestätigung wird in MFC verursacht werden, wenn sie festgelegt ist  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Control-Klasse registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dadurch wird die Eigenschaftenseite von Containern verwendet werden, die OLE-Steuerelements bekannt sind. `AfxOleRegisterPropertyPageClass`aktualisiert die Registrierung, die den Namen und den Speicherort auf dem System, und das threading-Modell, das das Steuerelement in der Registrierung unterstützt wird. Weitere Informationen finden Sie unter [Technische Hinweis 64](../../mfc/tn064-apartment-model-threading-in-activex-controls.md), "Apartmentmodell Threading in OLE-Steuerelemente," und [zu Prozessen und Threads](http://msdn.microsoft.com/library/windows/desktop/ms681917) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleregistertypelib"></a>AfxOleRegisterTypeLib  
 Die Typbibliothek mit der Datenbank der Windows-Registrierung registriert und können die Typbibliothek von anderen Containern verwendet werden, die OLE-Steuerelements bekannt sind.  
  
```   
BOOL AfxOleRegisterTypeLib(
    HINSTANCE hInstance,  
    REFGUID tlid,  
    LPCTSTR pszFileName = NULL,  
    LPCTSTR pszHelpDir  = NULL); 
```  
  
### <a name="parameters"></a>Parameter  
 `hInstance`  
 Der Instanzhandle der Anwendung, die der Typbibliothek zugeordnet.  
  
 *tlid*  
 Die eindeutige ID der Typbibliothek.  
  
 *pszFileName*  
 Der optionale Dateiname einer lokalisierten Typbibliothek verweist (. TLB)-Datei für das Steuerelement.  
  
 *pszHelpDir*  
 Der Name des Verzeichnisses, in dem die Hilfedatei für die Typbibliothek gefunden werden kann. Wenn **NULL**, wird angenommen, dass die Hilfedatei im gleichen Verzeichnis wie die Typbibliothek selbst sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Typbibliothek registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion aktualisiert die Registrierung mit dem Namen der Typbibliothek und den Speicherort auf dem System.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAutomation&#7;](../../mfc/codesnippet/cpp/registering-ole-controls_3.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation&#8;](../../mfc/codesnippet/cpp/registering-ole-controls_4.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  
  
##  <a name="afxoleunregisterclass"></a>AfxOleUnregisterClass  
 Entfernt den Eintrag Steuerelements oder einer Eigenschaft Seite Klasse aus der Datenbank der Windows-Registrierung.  
  
```   
BOOL AFXAPI AfxOleUnregisterClass(REFCLSID clsID, LPCSTR pszProgID); 
```  
  
### <a name="parameters"></a>Parameter  
 *clsID*  
 Die eindeutige Klassen-ID des Steuerelements oder der Eigenschaft.  
  
 `pszProgID`  
 Die eindeutige Programm-ID des Steuerelements oder der Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Seitenklasse Steuerelements oder einer Eigenschaft erfolgreich aufgehoben wurde; andernfalls 0.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxctl.h  
  
##  <a name="afxoleunregistertypelib"></a>AfxOleUnregisterTypeLib  
 Rufen Sie diese Funktion, um die Art "Bibliothek" aus der Datenbank der Windows-Registrierung zu entfernen.  
  
```   
BOOL AFXAPI AfxOleUnregisterTypeLib(REFGUID tlID); 
```  
  
### <a name="parameters"></a>Parameter  
 `tlID`  
 Die eindeutige ID der Typbibliothek.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Typbibliothek erfolgreich aufgehoben wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCAxCtl&#13;](../../mfc/reference/codesnippet/cpp/registering-ole-controls_5.cpp)]  

### <a name="requirements"></a>Anforderungen  
  **Header** afxdisp.h  

## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

