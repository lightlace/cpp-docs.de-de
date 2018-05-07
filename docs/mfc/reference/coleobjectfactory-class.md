---
title: COleObjectFactory-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleObjectFactory [MFC], COleObjectFactory
- COleObjectFactory [MFC], GetClassID
- COleObjectFactory [MFC], IsLicenseValid
- COleObjectFactory [MFC], IsRegistered
- COleObjectFactory [MFC], Register
- COleObjectFactory [MFC], RegisterAll
- COleObjectFactory [MFC], Revoke
- COleObjectFactory [MFC], RevokeAll
- COleObjectFactory [MFC], UnregisterAll
- COleObjectFactory [MFC], UpdateRegistry
- COleObjectFactory [MFC], UpdateRegistryAll
- COleObjectFactory [MFC], GetLicenseKey
- COleObjectFactory [MFC], OnCreateObject
- COleObjectFactory [MFC], VerifyLicenseKey
- COleObjectFactory [MFC], VerifyUserLicense
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd68493c9be5eb0bff63504cf49b38b9a2f216d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="coleobjectfactory-class"></a>COleObjectFactory-Klasse
Implementiert die OLE-Klassenfactory, die OLE-Objekte wie Server, Automatisierungsobjekte und Dokumente erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::COleObjectFactory](#coleobjectfactory)|Erstellt ein `COleObjectFactory`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::GetClassID](#getclassid)|Gibt die OLE Klassen-ID der Objekte, die von die dieser Factory erstellt.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Bestimmt, ob die Lizenz des Steuerelements gültig ist.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Gibt an, ob die Objektfactory für das OLE-System-DLLs registriert ist.|  
|[COleObjectFactory](#register)|Diese Objektfactory registriert OLE-System-DLLs.|  
|[COleObjectFactory::RegisterAll](#registerall)|Alle von der Anwendung Objektfactory registriert OLE-System-DLLs.|  
|[COleObjectFactory:: Revoke](#revoke)|Hebt diese Objektfactory Registrierung mit OLE-System-DLLs an.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Widerruft eine Anwendung Objekt Factorys Registrierungen mit der OLE-System-DLLs an.|  
|[UnregisterAll](#unregisterall)|Hebt die Registrierung aller Objektfactory für eine Anwendung.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Diese Objektfactory registriert OLE-systemregistrierung.|  
|[COleObjectFactory:: UpdateRegistryAll](#updateregistryall)|Registriert alle Objektfactory für die Anwendung mit der OLE-System-Registrierung.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Fordert einen eindeutigen Schlüssel in die DLL des Steuerelements an.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Vom Framework aufgerufen wird, ein neues Objekt des Typs von dieser Factory erstellen.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Überprüft, ob der Schlüssel in das Steuerelement eingebettet den Schlüssel im Container eingebettet übereinstimmt.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Stellt sicher, dass das Steuerelement für die Verwendung während der Entwurfszeit lizenziert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COleObjectFactory` -Klasse verfügt über Memberfunktionen zum Ausführen der folgenden Funktionen:  
  
-   Verwalten die Registrierung von Objekten.  
  
-   Aktualisieren das OLE-System-Register als auch die Laufzeit-Registrierung, die OLE darüber informiert, dass Objekte ausgeführt werden und zum Empfangen von Nachrichten bereit.  
  
-   Erzwingen die Lizenzierung durch Verwendung des Steuerelements für lizenzierte Entwickler zur Entwurfszeit und für lizenzierte Anwendungen zur Laufzeit zu beschränken.  
  
-   Registrieren Steuerelement-Objektfactory, bei der OLE-systemregistrierung.  
  
 Weitere Informationen zum Erstellen von Objekten finden Sie in den Artikeln [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md) und [Datenobjekte und Datenquellen: Erstellen und zerstören](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Weitere Informationen zur Registrierung finden Sie im Artikel [Registrierung](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 Erstellt ein `COleObjectFactory` Objekt, initialisiert es als eine nicht registrierte Objektfactory und fügt es der Liste der Factorys.  
  
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
 Verweis auf die OLE-Klassen-ID dieser Objektfactory darstellt.  
  
 `pRuntimeClass`  
 Ein Zeiger auf die Laufzeitklasse der C++-Objekte, die dieser Factory erstellen kann.  
  
 `bMultiInstance`  
 Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützen kann. Wenn **"true"**, werden mehrere Instanzen der Anwendung, die für jede Anforderung zum Erstellen eines Objekts gestartet.  
  
 `nFlags`  
 Enthält eine oder mehrere der folgenden Flags:  
  
- **AfxRegDefault** legt das Threadingmodell an ThreadingModel = Apartment.  
  
- **AfxRegInsertable** ermöglicht es dem Steuerelement angezeigt werden die **Objekt einfügen** im Dialogfeld für OLE-Objekte.  
  
- `afxRegApartmentThreading` Legt das Threadingmodell in der Registrierung auf ThreadingModel = Apartment.  
  
- **AfxRegFreeThreading** legt das Threadingmodell in der Registrierung auf ThreadingModel = frei.  
  
     Sie können die zwei Flags kombinieren `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = Both. Finden Sie unter [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) in das Windows SDK für Weitere Informationen zum Modell Registrierung threading.  
  
 `lpszProgID`  
 Zeiger auf eine Zeichenfolge, enthält ein verbale Programmbezeichner, z. B. "Microsoft Excel".  
  
### <a name="remarks"></a>Hinweise  
 Um das Objekt zu verwenden, müssen jedoch Sie sie registrieren.  
  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 Gibt einen Verweis auf die OLE-Klassen-ID, die diese Factory darstellt.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Verweis auf die OLE-Klassen-ID dieser Factory darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
 Fordert einen eindeutigen Lizenzschlüssel in die DLL des Steuerelements und speichert ihn in die `BSTR` verweist `pbstrKey`.  
  
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
 Ungleich NULL die Lizenzschlüssel Zeichenfolge ist nicht **NULL**, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion gibt 0 zurück und speichert Sie "nothing" in der `BSTR`. Wenn Sie MFC-ActiveX-Steuerelement verwenden, um das Projekt zu erstellen, liefert Steuerelement eine Außerkraftsetzung, die das Steuerelement-Lizenzschlüssel abruft.  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 Bestimmt, ob die Lizenz des Steuerelements gültig ist.  
  
```  
BOOL IsLicenseValid();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich; andernfalls "false".  
  
##  <a name="isregistered"></a>  COleObjectFactory::IsRegistered  
 Gibt einen Wert ungleich NULL zurück, wenn die Factory für die OLE-System-DLLs registriert ist.  
  
```  
virtual BOOL IsRegistered() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Factory registriert ist; andernfalls 0.  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 Wird aufgerufen, durch das Framework zum Erstellen eines neuen Objekts.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erstellte Objekt. Es kann eine Arbeitsspeicher-Ausnahme auslösen, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Erstellen des Objekts von etwas anders als die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) an den Konstruktor übergeben.  
  
##  <a name="register"></a>  COleObjectFactory  
 Diese Objektfactory registriert OLE-System-DLLs.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Factory wurde erfolgreich registriert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 Registriert alle Objektfactory für die Anwendung mit der OLE-System-DLLs.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Factorys erfolgreich registriert sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="revoke"></a>  COleObjectFactory:: Revoke  
 Hebt diese Objektfactory Registrierung mit OLE-System-DLLs an.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch ein, bevor die Anwendung beendet wird. Rufen Sie bei Bedarf mithilfe von einer Überschreibung von [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 Hebt alle von der Anwendung Objekt Factorys Registrierungen mit der OLE-System-DLLs.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch ein, bevor die Anwendung beendet wird. Rufen Sie bei Bedarf mithilfe von einer Überschreibung von [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="unregisterall"></a>  UnregisterAll  
 Hebt die Registrierung aller Objektfactory für eine Anwendung.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE.  
  
##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry  
 Registriert alle Objektfactory für die Anwendung mit der OLE-System-Registrierung.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszProgID`  
 Zeiger auf eine Zeichenfolge, enthält die lesbare Programm-ID, z. B. "Excel.Document.5."  
  
 `bRegister`  
 Bestimmt, ob der Steuerelement-Class-Objektfactory registriert werden.  
  
### <a name="remarks"></a>Hinweise  
 Führen Sie die kurze Diskussionen zu den beiden Formaten für diese Funktion:  
  
- **UpdateRegistry (** `lpszProgID` **)** dieser Objektfactory mit der OLE-systemregistrierung registriert. Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
- **UpdateRegistry (** `bRegister` **)** diese Form der Funktion ist überschreibbar. Wenn `bRegister` ist **"true"**, diese Funktion wird die Control-Klasse mit der Registrierung registriert. Andernfalls, hebt die Klasse Registrierung.  
  
     Wenn Sie MFC-ActiveX-Steuerelement verwenden, um das Projekt zu erstellen, liefert Steuerelement diese rein virtuelle Funktion überschreibt.  
  
##  <a name="updateregistryall"></a>  COleObjectFactory:: UpdateRegistryAll  
 Registriert alle Objektfactory für die Anwendung mit der OLE-System-Registrierung.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bRegister`  
 Bestimmt, ob der Steuerelement-Class-Objektfactory registriert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Factorys erfolgreich aktualisiert werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 Stellt sicher, dass der Container über die notwendige zum Verwenden des OLE-Steuerelements Lizenz.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 `bstrKey`  
 Ein `BSTR` des Containers Version der Lizenzzeichenfolge gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Lizenz zur Laufzeit gültig ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die Standard-Version [GetLicenseKey](#getlicensekey) abzurufenden eine Kopie des Steuerelements des Lizenzzeichenfolge und vergleicht ihn mit der Zeichenfolge in `bstrKey`. Wenn zwei Zeichenfolgen übereinstimmen, gibt die Funktion einen Wert ungleich NULL zurück. Andernfalls wird 0 zurückgegeben.  
  
 Sie können diese Funktion, um eine benutzerdefinierte Überprüfung der Lizenz überschreiben.  
  
 Die Funktion [VerifyUserLicense](#verifyuserlicense) die Lizenz zur Entwurfszeit überprüft.  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 Überprüft die während der Entwurfszeit-Lizenz für die OLE-Steuerelements an.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Lizenz zur Entwurfszeit gültig ist; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)
