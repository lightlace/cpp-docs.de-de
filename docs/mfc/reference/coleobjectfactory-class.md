---
title: COleObjectFactory-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 4d2ac698466709931259f1df28d6c75aa38b30f2
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850705"
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
|[COleObjectFactory::GetClassID](#getclassid)|Gibt die OLE Klassen-ID der Objekte, die diese Factory erstellt.|  
|[COleObjectFactory::IsLicenseValid](#islicensevalid)|Bestimmt, ob die Lizenz für das Steuerelement gültig ist.|  
|[COleObjectFactory::IsRegistered](#isregistered)|Gibt an, ob die Objektfactory für die OLE-System-DLLs registriert ist.|  
|[COleObjectFactory:: Register](#register)|Dieses Objekt-Factory registriert die OLE-System-DLLs.|  
|[COleObjectFactory::RegisterAll](#registerall)|Alle von der Anwendung Objekt Factorys registriert OLE-System-DLLs.|  
|[COleObjectFactory:: Revoke](#revoke)|Hebt die Registrierung dieser Objekt-Factory die OLE-System-DLLs.|  
|[COleObjectFactory::RevokeAll](#revokeall)|Hebt die Registrierungen Objektfactory einer Anwendung, mit der die OLE-System-DLLs.|  
|[COleObjectFactory:: UnregisterAll](#unregisterall)|Hebt die Registrierung aller Objektfactory für eine Anwendung.|  
|[COleObjectFactory::UpdateRegistry](#updateregistry)|Registriert dieses Objekt-Factory mit der Registrierung des OLE-Systems an.|  
|[COleObjectFactory:: UpdateRegistryAll](#updateregistryall)|Alle von der Anwendung Objekt Factorys registriert der OLE-systemregistrierung.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleObjectFactory::GetLicenseKey](#getlicensekey)|Fordert einen eindeutigen Schlüssel in die DLL des Steuerelements an.|  
|[COleObjectFactory::OnCreateObject](#oncreateobject)|Wird aufgerufen, durch das Framework um ein neues Objekt des Typs für diese Factory zu erstellen.|  
|[COleObjectFactory::VerifyLicenseKey](#verifylicensekey)|Überprüft, ob der Schlüssel in das Steuerelement eingebettet den Schlüssel im Container eingebettet entspricht.|  
|[COleObjectFactory::VerifyUserLicense](#verifyuserlicense)|Stellt sicher, dass das Steuerelement zur Entwurfszeit-Verwendung lizenziert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `COleObjectFactory` Klasse bietet Memberfunktionen zum Ausführen der folgenden Funktionen:  
  
-   Verwalten die Registrierung von Objekten.  
  
-   Aktualisieren das OLE-System-Register als auch die Run-Time-Registrierung, die OLE darüber informiert, dass Objekte ausgeführt werden und zum Empfangen von Nachrichten bereit.  
  
-   Erzwingen die Lizenzierung durch die Verwendung des Steuerelements für lizenzierte Entwickler zur Entwurfszeit und für lizenzierte Anwendungen zur Laufzeit zu beschränken.  
  
-   Registrieren Objektfactory Steuerelement, mit der OLE-System-Registrierung.  
  
 Weitere Informationen zum Erstellen von Objekten finden Sie unter den Artikeln [Datenobjekte und Datenquellen (OLE)](../../mfc/data-objects-and-data-sources-ole.md) und [Datenobjekte und Datenquellen: Erstellung und Zerstörung](../../mfc/data-objects-and-data-sources-creation-and-destruction.md). Finden Sie weitere Informationen zur Registrierung finden Sie im Artikel [Registrierung](../../mfc/registration.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleObjectFactory`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="coleobjectfactory"></a>  COleObjectFactory::COleObjectFactory  
 Erstellt eine `COleObjectFactory` Objekt, wie eine nicht registrierte Objektfactory initialisiert und fügt es der Liste mit Factorys hinzu.  
  
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
 *clsid*  
 Verweis auf die OLE-Klassen-ID, die diesem Objekt-Factory darstellt.  
  
 *pRuntimeClass*  
 Zeiger auf die Laufzeit-Klasse der C++-Objekte, die dieser Factory erstellen kann.  
  
 *bMultiInstance*  
 Gibt an, ob eine einzelne Instanz der Anwendung mehrere Instanziierungen unterstützt. Wenn "true" werden mehrere Instanzen der Anwendung für jede Anforderung zum Erstellen eines Objekts gestartet.  
  
 *nFlags*  
 Enthält eine oder mehrere der folgenden Flags:  
  
- `afxRegDefault` Legt das Threadingmodell auf ThreadingModel = Apartment.  
  
- `afxRegInsertable` Ermöglicht es dem Steuerelement angezeigt werden die **Objekt einfügen** im Dialogfeld für OLE-Objekte.  
  
- `afxRegApartmentThreading` Legt das threading-Modell in der Registrierung ThreadingModel = Apartment.  
  
- `afxRegFreeThreading` Legt das threading-Modell in der Registrierung ThreadingModel = frei.  
  
     Sie können die beiden Flags kombinieren `afxRegApartmentThreading` und `afxRegFreeThreading` festzulegende ThreadingModel = Both. Finden Sie unter [InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390) im Windows SDK für Weitere Informationen zum threading modellregistrierung.  
  
 *lpszProgID*  
 Zeiger auf eine Zeichenfolge, enthält ein mündliche Programmbezeichner, z. B. "Microsoft Excel."  
  
### <a name="remarks"></a>Hinweise  
 Um das Objekt verwenden zu können, müssen jedoch Sie ihn registrieren.  
  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="getclassid"></a>  COleObjectFactory::GetClassID  
 Gibt einen Verweis auf die OLE-Klassen-ID, die dieser Factory darstellt.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Verweis auf die OLE-Klassen-ID dieser Factory darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Schlüssel CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) im Windows SDK.  
  
##  <a name="getlicensekey"></a>  COleObjectFactory::GetLicenseKey  
 Die DLL des Steuerelements einen eindeutigen Lizenzschlüssel inhaltsortsanfrage und speichert sie in den BSTR verweist *PbstrKey*.  
  
```  
virtual BOOL GetLicenseKey(
    DWORD dwReserved,  
    BSTR* pbstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 *dwReserved*  
 Für zukünftige Verwendung reserviert.  
  
 *pbstrKey*  
 Zeiger auf ein BSTR, das den Lizenzschlüssel gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Zeichenfolge des Lizenzschlüssels nicht NULL ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung dieser Funktion gibt 0 zurück, und nichts in den BSTR. Wenn Sie die MFC-ActiveX-Steuerelement verwenden, um Ihr Projekt erstellen, stellt Assistent eine Außerkraftsetzung, die Lizenzschlüssel des Steuerelements abruft.  
  
##  <a name="islicensevalid"></a>  COleObjectFactory::IsLicenseValid  
 Bestimmt, ob die Lizenz für das Steuerelement gültig ist.  
  
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
 Ungleich NULL ist, wenn die Factory registriert ist; andernfalls 0.  
  
##  <a name="oncreateobject"></a>  COleObjectFactory::OnCreateObject  
 Wird aufgerufen, durch das Framework zum Erstellen eines neuen Objekts.  
  
```  
virtual CCmdTarget* OnCreateObject();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erstellte Objekt. Sie können eine Arbeitsspeicher-Ausnahme auslösen, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion zum Erstellen des Objekts von etwas anders als die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) an den Konstruktor übergeben.  
  
##  <a name="register"></a>  COleObjectFactory:: Register  
 Dieses Objekt-Factory registriert die OLE-System-DLLs.  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Factory erfolgreich registriert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="registerall"></a>  COleObjectFactory::RegisterAll  
 Registriert alle von der Anwendung Objekt Factorys mit dem OLE-System-DLLs.  
  
```  
static BOOL PASCAL RegisterAll();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Factorys erfolgreich registriert sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="revoke"></a>  COleObjectFactory:: Revoke  
 Hebt die Registrierung dieser Objekt-Factory die OLE-System-DLLs.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch, bevor die Anwendung beendet wird. Rufen Sie es ggf. von einer Überschreibung von [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="revokeall"></a>  COleObjectFactory::RevokeAll  
 Es sperrt alle von der Anwendung Objekt Factorys Registrierungen mit der OLE-System-DLLs.  
  
```  
static void PASCAL RevokeAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion automatisch, bevor die Anwendung beendet wird. Rufen Sie es ggf. von einer Überschreibung von [CWinApp:: ExitInstance](../../mfc/reference/cwinapp-class.md#exitinstance).  
  
##  <a name="unregisterall"></a>  COleObjectFactory:: UnregisterAll  
 Hebt die Registrierung aller Objektfactory für eine Anwendung.  
  
```  
static BOOL PASCAL UnregisterAll();
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn erfolgreich, andernfalls FALSE.  
  
##  <a name="updateregistry"></a>  COleObjectFactory::UpdateRegistry  
 Alle von der Anwendung Objekt Factorys registriert der OLE-systemregistrierung.  
  
```  
void UpdateRegistry(LPCTSTR lpszProgID = NULL);  
virtual BOOL UpdateRegistry(BOOL bRegister);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszProgID*  
 Zeiger auf eine Zeichenfolge, enthält die lesbare Programm-ID, z. B. "Excel.Document.5."  
  
 *bRegistrieren Sie sich*  
 Bestimmt, ob der Steuerelement-Class-Objektfactory registriert werden.  
  
### <a name="remarks"></a>Hinweise  
 Führen Sie die kurze erläuterungen zu den zwei Formen für diese Funktion:  
  
- **UpdateRegistry (** `lpszProgID` **)** dieser Objektfactory mit der OLE-System-Registrierung registriert. Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
- **UpdateRegistry (** `bRegister` **)** diese Form der Funktion ist überschreibbar. Wenn *bRegistrieren Sie sich* ist "true", diese Funktion registriert, die das Steuerelement-Klasse mit der Registrierung des Systems. Andernfalls, hebt die Registrierung für sie der Klasse.  
  
     Wenn Sie die MFC-ActiveX-Steuerelement verwenden, um Ihr Projekt erstellen, stellt Assistent diese rein virtuelle Funktion überschreibt.  
  
##  <a name="updateregistryall"></a>  COleObjectFactory:: UpdateRegistryAll  
 Alle von der Anwendung Objekt Factorys registriert der OLE-systemregistrierung.  
  
```  
static BOOL PASCAL UpdateRegistryAll(BOOL bRegister = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bRegistrieren Sie sich*  
 Bestimmt, ob der Steuerelement-Class-Objektfactory registriert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Factorys erfolgreich aktualisiert wurden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in der Regel aufgerufen, indem [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) beim Start der Anwendung.  
  
##  <a name="verifylicensekey"></a>  COleObjectFactory::VerifyLicenseKey  
 Stellt sicher, dass der Container, zur Verwendung des OLE-Steuerelements lizenziert ist.  
  
```  
virtual BOOL VerifyLicenseKey(BSTR bstrKey);
```  
  
### <a name="parameters"></a>Parameter  
 *bstrKey*  
 BSTR, speichern die Version des Containers der Lizenzzeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Laufzeit-Lizenz gültig ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die Standard-Version [GetLicenseKey](#getlicensekey) , eine Kopie des Steuerelements erhalten die Lizenzzeichenfolge und vergleicht ihn mit der Zeichenfolge in *BstrKey*. Wenn die beiden Zeichenfolgen übereinstimmen, gibt die Funktion einen Wert ungleich NULL zurück. Andernfalls wird 0 zurückgegeben.  
  
 Sie können diese Funktion, um die benutzerdefinierte Überprüfung für die Lizenz überschreiben.  
  
 Die Funktion [VerifyUserLicense](#verifyuserlicense) überprüft die Entwurfszeit-Lizenz.  
  
##  <a name="verifyuserlicense"></a>  COleObjectFactory::VerifyUserLicense  
 Überprüft, die während der Entwurfszeit-Lizenz für die OLE-Steuerelements.  
  
```  
virtual BOOL VerifyUserLicense();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Entwurfszeit-Lizenz gültig ist; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer-Klasse](../../mfc/reference/coletemplateserver-class.md)
