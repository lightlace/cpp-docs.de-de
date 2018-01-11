---
title: 'TN054: DAO bei der Verwendung von MFC-DAO-Klassen direkt aufrufen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.dao
dev_langs: C++
helpviewer_keywords:
- MFC, DAO and
- passwords [MFC], calling DAO
- security [MFC], DAO
- DAO (Data Access Objects), calling directly
- DAO (Data Access Objects), security
- security [MFC]
- TN054
- DAO (Data Access Objects), and MFC
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de49cec931878cbfe06939269721b17a37a66202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: DAO bei der Verwendung von MFC-DAO-Klassen direkt aufrufen
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützt nicht DAO (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
 Wenn Sie die MFC-DAO-Datenbankklassen verwenden zu können, möglicherweise gibt es Situationen, in denen es erforderlich, DAO direkt zu verwenden ist. In der Regel wird dies nicht der Fall sein, aber einige Helper-Mechanismen zum direkte DAO aufrufen einfache zu erleichtern, beim Kombinieren der Verwendung von MFC-Klassen mit direkten Aufrufen von DAO von MFC bereitgestellt hat. Direkte DAO sollte Aufrufen der Methoden eines Objekts verwaltete MFC-DAO nur wenige Codezeilen erfordert. Wenn Sie benötigen zum Erstellen und Verwenden von DAO-Objekte, die *nicht* von MFC verwaltet werden, müssen Sie ein wenig mehr Arbeit tatsächlich aufrufen Zweck **Version** für das Objekt. In diesem technischen Hinweis wird erläutert, wenn Sie DAO direkt aufrufen möchten, die MFC-Hilfsprogramme Möglichkeiten, die Sie unterstützen, sowie zum DAO OLE-Schnittstellen verwenden. Schließlich stellt dieser Hinweis Einige Beispielfunktionen, die zum Aufrufen von DAO direkt für DAO-Sicherheitsfunktionen.  
  
## <a name="when-to-make-direct-dao-calls"></a>Beim direkten DAO-Aufrufe ausführen  
 Die am häufigsten verwendeten Situationen zum treffen von DAO-Aufrufe weiterleiten auftreten, wenn Sammlungen müssen aktualisiert werden, oder Sie werden beim Implementieren von Funktionen, die von MFC nicht umschlossen wird. Das wichtigste Feature von MFC nicht verfügbar gemacht wird Sicherheit. Wenn Sie die Sicherheitsfunktionen implementieren möchten, müssen Sie die Objekte DAO von Benutzern und Gruppen direkt verwenden. Neben Sicherheit es sind nur einigen andere DAO-Funktionen von MFC nicht unterstützt. Dazu zählen das Klonen und die Datenbank-Replikationsfunktionen Recordset sowie einige spät Ergänzungen für DAO.  
  
## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>Eine kurze Übersicht über DAO und MFC Implementierung  
 MFC Wrapping DAO gestaltet sich einfacher mithilfe von DAO durch viele der Details behandeln können, müssen Sie nicht über die Dinge Gedanken machen. Dies schließt die Initialisierung von OLE, die Erstellung und Verwaltung von den DAO-Objekten (insbesondere die Auflistungsobjekte), Fehler überprüfen und eine stark typisierte, einfachere Schnittstelle bereitstellt (keine **VARIANT** oder `BSTR` Argumente). Sie können direkte Aufrufe von DAO und dennoch diese Funktionen nutzen. Ihr Code ausführen muss lediglich Aufruf **Release** für alle Objekte erstellt, indem direkte DAO aufruft und *nicht* ändern Sie den Schnittstellenzeiger, der MFC intern basieren kann. Ändern Sie z. B. nicht die **M_pDAORecordset** Mitglied ein offenes `CDaoRecordset` -Objekt, es sei denn, Sie wissen *alle* die interne Auswirkungen. Sie können jedoch verwenden, die **M_pDAORecordset** Schnittstelle Aufrufen von DAO direkt, um die Fields-Auflistung erhalten. In diesem Fall die **M_pDAORecordset** Element würde nicht geändert werden. Müssen Sie einfach anrufen **Version** auf das Sammlungsobjekt Felder, wenn Sie mit dem Objekt fertig sind.  
  
## <a name="description-of-helpers-to-make-dao-calls-easier"></a>Beschreibung der Hilfsprogramme DAO vornehmen aufruft einfacher  
 Zum Aufrufen von DAO einfacher stellen Hilfsprogramme sind die gleichen Hilfsprogramme, die intern in der MFC-DAO-Datenbankklassen verwendet werden. Diese Hilfsprogramme werden zum Überprüfen der Rückgabecodes beim Herstellen eines direkten DAO-Aufrufs Debugausgabe, Protokollierung, erwartete Fehler überprüfen und entsprechende Ausnahmen auslösen, bei Bedarf. Es gibt zwei zugrunde liegende Hilfsfunktionen und vier Makros, die auf einen der folgenden zwei Hilfsmethoden zuordnen. Die beste Erklärung wäre, den Code einfach zu lesen. Finden Sie unter **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**, und **DAO_TRACE** in AFXDAO. H, um die Makros, anzuzeigen und **AfxDaoCheck** und **AfxDaoTrace** in DAOCORE. CPP.  
  
## <a name="using-the-dao-ole-interfaces"></a>Verwenden die DAO-OLE-Schnittstellen  
 Die OLE-Schnittstellen für jedes Objekt in der Objekthierarchie DAO werden in der Headerdatei DBDAOINT definiert. H, die sich im Verzeichnis \Programme\Microsoft Visual Studio .NET 2003\VC7\include befindet. Diese Schnittstellen bieten Methoden, mit die Sie die gesamte DAO-Hierarchie bearbeiten können.  
  
 Für viele der Methoden in den DAO-Schnittstellen, müssen Sie zum Bearbeiten einer `BSTR` Objekt (ein Längenpräfix Zeichenfolge, die in der OLE-Automatisierung verwendet). Die `BSTR` Objekt in der Regel ist Teil der **VARIANT** -Datentyp. Die MFC-Klasse `COleVariant` selbst erbt von der **VARIANT** -Datentyp. Je nachdem, ob des Projekts für ANSI oder Unicode erstellen zurück die DAO-Schnittstellen ANSI- oder Unicode- `BSTR`s. Zwei Makros **V_BSTR** und **V_BSTRT**, eignen sich für sichergestellt wird, dass die DAO-Schnittstelle ruft die `BSTR` vom erwarteten Typ.  
  
 **V_BSTR** extrahiert die **BstrVal** Mitglied einer `COleVariant`. Dieses Makro wird in der Regel verwendet, wenn Sie den Inhalt des übergeben müssen eine `COleVariant` an eine Methode einer DAO-Schnittstelle. Das folgende Codefragment zeigt sowohl die tatsächliche Verwendung für die zwei Methoden für die DAO-DAOUser-Schnittstelle, die nutzen die Deklarationen der **V_BSTR** Makro:  
  
```  
COleVariant varOldName;  
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

 
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
 
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
 
DAO_CHECK(pUser->get_Name(&V_BSTR (&varOldName)));

DAO_CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```  
  
 Beachten Sie, dass die `VT_BSTRT` angegebene Argument in der `COleVariant` Konstruktor oben wird sichergestellt, dass sich ein ANSI `BSTR` in der `COleVariant` , wenn Sie eine ANSI-Version und eine Unicode-Anwendung erstellen `BSTR` für eine Unicode-Version die Anwendung. Dies ist, was DAO erwartet.  
  
 Das Makro andere **V_BSTRT**, wird entweder eine ANSI- oder Unicode-extrahiert **BstrVal** Mitglied `COleVariant` je nach Art des Builds (ANSI oder Unicode). Der folgende Code zeigt das Extrahieren der `BSTR` Wert aus einer `COleVariant` in einer `CString`:  
  
```  
COleVariant varName(_T("MyName"), VT_BSTRT);

CString str = V_BSTRT(&varName);
```  
  
 Die **V_BSTRT** -Makro, zusammen mit anderen Techniken, mit denen andere Typen zu öffnen, die im rowsetcache `COleVariant`, wird im DAOVIEW-Beispiel veranschaulicht. Insbesondere erfolgt diese Übersetzung in die **CCrack::strVARIANT** Methode. Diese Methode möglichst übersetzt den Wert von einem `COleVariant` in eine Instanz von `CString`.  
  
## <a name="simple-example-of-a-direct-call-to-dao"></a>Einfaches Beispiel für einen direkten Aufruf von DAO  
 Bei Bedarf die zugrunde liegenden DAO Auflistungsobjekte aktualisieren, können Situationen auftreten. In der Regel wird dies sollte nicht erforderlich sein, aber es ist eine einfache Prozedur, wenn es erforderlich ist. Ein Beispiel, wenn eine Auflistung möglicherweise aktualisiert werden muss, ist während des Betriebs in einer mehrbenutzerumgebung mit mehreren Benutzern neue Tabledefs erstellen. In diesem Fall möglicherweise Tabledefs-Auflistung veralten. Um der Auflistung zu aktualisieren, müssen Sie nur zum Aufrufen der **aktualisieren** Methode der bestimmten Auflistungsobjekt und prüfen Sie nach Fehlern:  
  
```  
DAO_CHECK(pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh());
```  
  
 Beachten Sie, dass derzeit alle DAO Auflistungsschnittstellen Objekt nicht dokumentierten Implementierungsdetails der MFC-DAO-Datenbankklassen.  
  
## <a name="using-dao-directly-for-dao-security-features"></a>Mithilfe von DAO direkt für DAO-Sicherheitsfunktionen  
 Die MFC-DAO-Datenbankklassen Zeilenumbruch DAO-Sicherheitsfunktionen kein. Rufen Sie die Methoden von DAO-Schnittstellen, einige DAO-Sicherheitsfunktionen verwenden. Die folgende Funktion legt die Systemdatenbank und ändert dann das Kennwort des Benutzers. Diese Funktion ruft drei anderen Funktionen, die anschließend definiert sind.  
  
```  
void ChangeUserPassword()  
{ *// Specify path to the Microsoft Access *// system database  
    CString strSystemDB = 
    _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

 *// Set system database before MFC initilizes DAO *// NOTE: An MFC module uses only one instance *// of a DAO database engine object. If you have *// called a DAO object in your application prior *// to calling the function below,
    you must call *// AfxDaoTerm to destroy the existing database *// engine object. Otherwise,
    the database engine *// object already in use will be reused,
    and setting *// a system datbase will have no effect. *// *// If you have used a DAO object prior to calling *// this function it is important that DAO be *// terminated with AfxDaoTerm since an MFC *// module only gets one copy of the database engine *// and that engine will be reused if it hasn't been *// terminated. In other words,
    if you do not call *// AfxDaoTerm and there is currently a database *// initialized,
    setting the system database will *// have no affect.  
 
    SetSystemDB(strSystemDB);

 *// User name and password manually added *// by using Microsoft Access  
    CString strUserName = _T("NewUser");

    CString strOldPassword = _T("Password");

    CString strNewPassword = _T("NewPassword");

 *// Set default user so that MFC will be able *// to log in by default using the user name and *// password from the system database  
    SetDefaultUser(strUserName,
    strOldPassword);

 *// Change the password. You should be able to *// call this function from anywhere in your *// MFC application  
    ChangePassword(strUserName,
    strOldPassword,   
    strNewPassword);

 
 .  
 .  
 .  
 
}  
```  
  
 Die nächsten vier Beispielen wird gezeigt, wie Sie:  
  
-   Legen Sie die DAO-Systemdatenbank (. MDW-Datei).  
  
-   Legen Sie den Standard-Benutzer und das Kennwort ein.  
  
-   Ändern Sie das Kennwort eines Benutzers.  
  
-   Ändern Sie das Kennwort ein. MDB-Datei.  
  
### <a name="setting-the-system-database"></a>Festlegen der Systemdatenbank  
 Es folgt eine Beispielfunktion die Systemdatenbank festlegen, die von einer Anwendung verwendet werden soll. Diese Funktion muss aufgerufen werden, bevor andere DAO-Aufrufe erfolgen.  
  
```  
// Set the system database that the   
// DAO database engine will use  
 
void SetSystemDB(CString& strSystemMDB)  
{  
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

 *// Initialize DAO for MFC  
    AfxDaoInit();
DAODBEngine* pDBEngine = AfxDaoGetEngine();

 
    ASSERT(pDBEngine != NULL);

 *// Call put_SystemDB method to set the *// system database for DAO engine  
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));

} 
```  
  
### <a name="setting-the-default-user-and-password"></a>Festlegen der Standard-Benutzer und Kennwort  
 Um die Standard-Benutzer und das Kennwort für eine Systemdatenbank festzulegen, verwenden Sie die folgende Funktion:  
  
```  
void SetDefaultUser(CString& strUserName,
    CString& strPassword)  
{  
    COleVariant varUserName(strUserName,
    VT_BSTRT);

    COleVariant varPassword(strPassword,
    VT_BSTRT);

 
    DAODBEngine* pDBEngine = AfxDaoGetEngine();
ASSERT(pDBEngine != NULL);

 *// Set default user:  
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

 *// Set default password:  
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));

} 
```  
  
### <a name="changing-a-users-password"></a>Ändern das Kennwort eines Benutzers  
 Um das Kennwort eines Benutzers zu ändern, verwenden Sie die folgende Funktion:  
  
```  
void ChangePassword(CString &strUserName,   
    CString &strOldPassword,   
    CString &strNewPassword)  
{ *// Create (open) a workspace  
    CDaoWorkspace wsp;  
    CString strWspName = _T("Temp Workspace");

 
    wsp.Create(strWspName, strUserName,  
    strOldPassword);

 wsp.Append();

 *// Determine how many objects there are *// in the Users collection  
    short nUserCount;  
    short nCurrentUser;  
    DAOUser *pUser = NULL;  
    DAOUsers *pUsers = NULL;  
 *// Side-effect is implicit OLE AddRef() *// on DAOUser object:  
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

 *// Side-effect is implicit OLE AddRef() *// on DAOUsers object  
    DAO_CHECK(pUsers->getcount(&nUserCount));

 *// Traverse through the list of users *// and change password for the userid *// used to create/open the workspace  
    for(nCurrentUser = 0; nCurrentUser <nUserCount;  
    nCurrentUser++) 
 {  
    COleVariant varIndex(nCurrentUser, VT_I2);

    COleVariant varName;  
 *// Retrieve information for user nCurrentUser  
    DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

 *// Retrieve name for user nCurrentUser  
    DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

 
    CString strTemp = V_BSTRT(&varName);

 *// If there is a match, change the password  
    if(strTemp == strUserName)  
 {  
    COleVariant varOldPwd(strOldPassword,   
    VT_BSTRT);

 COleVariant  varNewPwd(strNewPassword,   
    VT_BSTRT);

 
    DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd), 
    V_BSTR(&varNewPwd)));

 
    TRACE("\t Password is changed\n");

 }  
 }  
 *// Clean up: decrement the usage count *// on the OLE objects  
    pUser->Release();
pUsers->Release();

 
    wsp.Close();

} 
```  
  
### <a name="changing-the-password-of-an-mdb-file"></a>Ändern des Kennworts ein. MDB-Datei  
 So ändern Sie das Kennwort ein. MDB-Datei, verwenden Sie die folgende Funktion:  
  
```  
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)  
{  
    CDaoDatabase db;  
    CString strConnect(_T(";pwd="));

 *// the database must be opened as exclusive *// to set a password  
    db.Open(pDB,
    TRUE,
    FALSE,   
    strConnect + pszOldPassword);

 
    COleVariant NewPassword(pszNewPassword,
    VT_BSTRT),  
    OldPassword(pszOldPassword,
    VT_BSTRT);

 
    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword), 
    V_BSTR(&NewPassword)));

 
    db.Close();

} 
```  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

