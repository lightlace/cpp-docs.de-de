---
title: COleObjectFactory-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleObjectFactory
- AFXDISP/COleObjectFactory
- AFXDISP/COleObjectFactory::COleObjectFactory
- AFXDISP/COleObjectFactory::GetClassID
- AFXDISP/COleObjectFactory::IsLicenseValid
- AFXDISP/COleObjectFactory::IsRegistered
- AFXDISP/COleObjectFactory::Register
- AFXDISP/COleObjectFactory::RegisterAll
- AFXDISP/COleObjectFactory::Revoke
- AFXDISP/COleObjectFactory::RevokeAll
- AFXDISP/COleObjectFactory::UnregisterAll
- AFXDISP/COleObjectFactory::UpdateRegistry
- AFXDISP/COleObjectFactory::UpdateRegistryAll
- AFXDISP/COleObjectFactory::GetLicenseKey
- AFXDISP/COleObjectFactory::OnCreateObject
- AFXDISP/COleObjectFactory::VerifyLicenseKey
- AFXDISP/COleObjectFactory::VerifyUserLicense
dev_langs:
- C++
helpviewer_keywords:
- OLE, class factory
- OLE class factory
- COleObjectFactory class
- objects [C++], creating OLE
- OLE objects
- object creation, OLE objects
- class factories, COleObjectFactory class
- OLE objects, creating
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
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
ms.openlocfilehash: 643d17ccdefb60b561e7e5488753a6dbf778c69f
ms.lasthandoff: 02/24/2017

---
# <a name="coleobjectfactory-class"></a>COleObjectFactory-Klasse
Implementiert die OLE-Klassenfactory, die OLE-Objekte wie Server, Automatisierungsobjekte und Dokumente erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Erstellt ein `COleObjectFactory`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|Gibt die OLE Klassen-ID der Objekte, die diese Factory erstellt.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Bestimmt, ob die Lizenz des Steuerelements gültig ist.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Gibt an, ob die Objektfactory für die OLE-System-DLLs registriert ist.|  
|[COleObjectFactory:: Register](#register)|Dieses Objekt-Factory registriert die OLE-System-DLLs.|  
|[COleObjectFactory::RegisterAll](#registerall)|Alle von der Anwendung Objektfactory registriert OLE-System-DLLs.|  
|[COleObjectFactory:: Revoke](#revoke)|Widerruft dieses Objekt-Factory-Registrierung mit OLE-System-DLLs.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Widerruft eine Anwendung Objekt Factorys Registrierungen mit der OLE-System-DLLs.|  
|[UnregisterAll](#unregisterall)|Hebt die Registrierung aller Objektfactory für eine Anwendung.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Dieses Objekt-Factory registriert die OLE-System-Registrierung.|  
|[COleObjectFactory:: UpdateRegistryAll](#updateregistryall)|Registriert alle Objektfactory für die Anwendung mit der OLE-System-Registrierung.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Fordert einen eindeutigen Schlüssel von der Steuerelement-DLL an.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Aufgerufen, um ein neues Objekt des Typs dieser Factory zu erstellen.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Überprüft, ob der Schlüssel in das Steuerelement eingebettet den Schlüssel im Container eingebettet übereinstimmt.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Stellt sicher, dass das Steuerelement zur Entwurfszeit-Verwendung lizenziert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COleObjectFactory` Klasse bietet Memberfunktionen zum Ausführen der folgenden Funktionen:  
  
-   Verwalten der Registrierung von Objekten.  
  
-   Aktualisieren das OLE-System-Register als auch die Laufzeit-Registrierung, die OLE darüber informiert, dass Objekte ausgeführt werden und zum Empfangen von Nachrichten bereit.  
  
-   Erzwingen die Lizenzierung durch die Begrenzung des Steuerelements für lizenzierte Entwickler zur Entwurfszeit und lizenzierte Anwendungen zur Laufzeit verwenden.  
  
-   Registrieren mit der OLE-System-Registrierung Steuerelement Objektfactory.  
  
 Weitere Informationen zu erstellen, finden Sie in den Artikeln [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md) und [Datenobjekte und Datenquellen: Erstellung und Zerstörung](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Weitere Informationen zur Registrierung finden Sie im Artikel [Registrierung](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>COleObjectFactory::COleObjectFactory  
 Erstellt ein `COleObjectFactory` -Objekt, initialisiert es als eine Objektfactory aufgehoben, und die Liste der Factorys hinzugefügt.  
  
```  
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    LPCTSTR lpszProgID);

 
COleObjectFactory(
    REFCLSID clsid,  
    CRuntimeClass* pRuntimeClass,  
    BOOL bMultiInstance,  
    int nFlags,  
    LPCTSTR lpszProgID);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Verweis auf die OLE-Klassen-ID, die dieses Objektfactory darstellt.  
  
 `pRuntimeClass`  
 Ein Zeiger auf die Laufzeitklasse der C++-Objekte, die diese Factory erstellen kann.  
  
 `bMultiInstance`  
 Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützen kann. Wenn **TRUE**, mehrere Instanzen der Anwendung werden für jede Anforderung zum Erstellen eines Objekts gestartet.  
  
 `nFlags`  
 Enthält eine oder mehrere der folgenden Flags:  
  
- **AfxRegDefault** legt das Threadingmodell auf ThreadingModel = Apartment.  
  
- **AfxRegInsertable** ermöglicht es dem Steuerelement angezeigt werden die **Objekt einfügen** für OLE-Objekte im Dialogfeld.  
  
- `afxRegApartmentThreading`Legt das Threadingmodell in der Registrierung ThreadingModel = Apartment.  
  
- **AfxRegFreeThreading** legt das Threadingmodell in der Registrierung ThreadingModel = frei.  
  
     Die zwei Flags können kombiniert werden `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = beides. Finden Sie unter [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen über threading-Modell-Registrierung.  
  
 `lpszProgID`  
 Zeiger auf eine Zeichenfolge mit einem verbalen Programmbezeichner, z. B. "Microsoft Excel".  
  
### <a name="remarks"></a>Hinweise  
 Um das Objekt zu verwenden, müssen jedoch Sie ihn registrieren.  
  
 Weitere Informationen finden Sie unter [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getclassid"></a>COleObjectFactory::GetClassID  
 Gibt einen Verweis auf die OLE-Klassen-ID, die diese Factory darstellt.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Verweis auf die OLE-Klassen-ID dieser Factory darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CLSID-Schlüssel](http://msdn.microsoft.com/library/windows/desktop/ms691424) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlicensekey"></a>COleObjectFactory::GetLicenseKey  
 Fordert einen eindeutigen Lizenzschlüssel in die DLL und speichert ihn in der `BSTR` auf den `pbstrKey`.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 `dwReserved`  
 Für zukünftige Verwendung reserviert.  
  
 `pbstrKey`  
 Zeiger auf eine `BSTR` den Lizenzschlüssel gespeichert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Zeichenfolge Lizenzschlüssels nicht ist **NULL**; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion gibt 0 zurück und speichert Sie in der `BSTR`. Wenn Sie MFC-ActiveX-Steuerelement verwenden, um das Projekt zu erstellen, stellt Steuerelement eine Außerkraftsetzung, die das Steuerelement Lizenzschlüssel abruft.  
  
##  <a name="islicensevalid"></a>COleObjectFactory::IsLicenseValid  
 Bestimmt, ob die Lizenz des Steuerelements gültig ist.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich; andernfalls False.  
  
##  <a name="isregistered"></a>COleObjectFactory::IsRegistered  
 Gibt einen Wert ungleich NULL zurück, wenn die Factory für die OLE-System-DLLs registriert ist.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Factory registriert ist; andernfalls 0.  
  
##  <a name="oncreateobject"></a>COleObjectFactory::OnCreateObject  
 Aufgerufen, um ein neues Objekt zu erstellen.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erstellte Objekt. Sie können eine Speicherausnahme auslösen, bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Erstellen des Objekts von einer anderen als der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) an den Konstruktor übergeben.  
  
##  <a name="register"></a>COleObjectFactory:: Register  
 Dieses Objekt-Factory registriert die OLE-System-DLLs.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Factory erfolgreich registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="registerall"></a>COleObjectFactory::RegisterAll  
 Registriert alle Objektfactory für die Anwendung mit der OLE-System-DLLs.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Factorys erfolgreich registriert sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="revoke"></a>COleObjectFactory:: Revoke  
 Widerruft dieses Objekt-Factory-Registrierung mit OLE-System-DLLs.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch, bevor die Anwendung beendet wird. Rufen Sie es ggf. von einer Überschreibung von [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="revokeall"></a>COleObjectFactory::RevokeAll  
 Hebt alle von der Anwendung Objekt Factorys Registrierungen mit der OLE-System-DLLs.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch, bevor die Anwendung beendet wird. Rufen Sie es ggf. von einer Überschreibung von [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="unregisterall"></a>UnregisterAll  
 Hebt die Registrierung aller Objektfactory für eine Anwendung.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE.  
  
##  <a name="updateregistry"></a>COleObjectFactory::UpdateRegistry  
 Registriert alle Objektfactory für die Anwendung mit der OLE-System-Registrierung.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProgID`  
 Zeiger auf eine Zeichenfolge, die die lesbare Programm-ID, wie z. B. "Excel.Document.5."  
  
 `bRegister`  
 Bestimmt, ob die Control-Klasse Objektfactory registriert werden.  
  
### <a name="remarks"></a>Hinweise  
 Führen Sie die kurze Diskussionen über die beiden Formulare für diese Funktion:  
  
- **UpdateRegistry (** `lpszProgID` **)** dieses Objekt-Factory mit der OLE-System-Registrierung registriert. Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
- **UpdateRegistry (** `bRegister` **)** diese Form der Funktion ist überschreibbar. Wenn `bRegister` ist **TRUE**, diese Funktion die Control-Klasse mit der Registrierung registriert. Andernfalls hebt es die-Klasse.  
  
     Wenn Sie MFC-ActiveX-Steuerelement verwenden, um das Projekt zu erstellen, stellt Assistent überschreibt diese rein virtuelle Funktion.  
  
##  <a name="updateregistryall"></a>COleObjectFactory:: UpdateRegistryAll  
 Registriert alle Objektfactory für die Anwendung mit der OLE-System-Registrierung.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bRegister`  
 Bestimmt, ob die Control-Klasse Objektfactory registriert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Factorys erfolgreich aktualisiert werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="verifylicensekey"></a>COleObjectFactory::VerifyLicenseKey  
 Stellt sicher, dass der Container zum Verwenden des OLE-Steuerelements lizenziert ist.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 `bstrKey`  
 Ein `BSTR` des Containers Version der Lizenzzeichenfolge gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Laufzeit-Lizenz gültig ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Standard-Version-Aufrufe [GetLicenseKey](#getlicensekey) eine Kopie des Steuerelements Abrufen des Lizenzzeichenfolge und vergleicht sie mit der Zeichenfolge in `bstrKey`. Wenn die beiden Zeichenfolgen übereinstimmen, gibt die Funktion einen Wert ungleich NULL zurück. Andernfalls wird 0 zurückgegeben.  
  
 Sie können diese Funktion, um benutzerdefinierte Überprüfung der Lizenz überschreiben.  
  
 Die Funktion [VerifyUserLicense](#verifyuserlicense) überprüft die Entwurfszeit-Lizenz.  
  
##  <a name="verifyuserlicense"></a>COleObjectFactory::VerifyUserLicense  
 Überprüft die Entwurfszeit-Lizenz für das OLE-Steuerelement.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Entwurfszeit-Lizenz gültig ist; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)

