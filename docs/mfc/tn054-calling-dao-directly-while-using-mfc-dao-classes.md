---
title: 'TN054: Direktes Aufrufen von DAO bei Verwendung von MFC-DAO-Klassen'
ms.date: 09/17/2019
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
ms.openlocfilehash: cef9852f762a64579e11fe4b0d8606bfc9d36709
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095978"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: Direktes Aufrufen von DAO bei Verwendung von MFC-DAO-Klassen

> [!NOTE]
> DAO wird für Access-Datenbanken verwendet und wird von Office 2013 unterstützt. 3,6 ist die endgültige Version und wird als veraltet eingestuft. Die visuelle C++ Umgebung und die Assistenten unterstützen DAO nicht (obwohl die DAO-Klassen eingeschlossen sind und Sie Sie weiterhin verwenden können). Microsoft empfiehlt, [OLE DB Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte zu verwenden. Sie sollten DAO nur für die Wartung vorhandener Anwendungen verwenden.

Wenn Sie die MFC-DAO-Datenbankklassen verwenden, kann es Situationen geben, in denen DAO direkt verwendet werden muss. Normalerweise ist dies nicht der Fall, aber MFC hat einige Hilfsmechanismen bereitgestellt, um die direkte Verwendung von DAO-aufrufen beim Kombinieren der MFC-Klassen mit direkten DAO-aufrufen zu vereinfachen. Direkte DAO-Aufrufe an die Methoden eines von MFC verwalteten DAO-Objekts sollten nur einige wenige Codezeilen erfordern. Wenn Sie DAO-Objekte erstellen und verwenden müssen, die *nicht* von MFC verwaltet werden, müssen Sie etwas mehr Arbeit durchführen, indem Sie für `Release` das-Objekt aufrufen. Dieser Technische Hinweis erläutert, wann DAO direkt aufgerufen werden kann, was die MFC-Hilfsprogramme tun können, um Sie zu unterstützen und wie die DAO-OLE-Schnittstellen verwendet werden. Schließlich enthält diese Notiz einige Beispiel Funktionen, die zeigen, wie DAO direkt für DAO-Sicherheitsfeatures aufgerufen wird.

## <a name="when-to-make-direct-dao-calls"></a>Wann direkte DAO-Aufrufe durchführen werden

Die gängigsten Situationen für direkte DAO-Aufrufe treten auf, wenn Sammlungen aktualisiert werden müssen oder wenn Sie Funktionen implementieren, die nicht von MFC umschließt werden. Das wichtigste Feature, das von MFC nicht verfügbar gemacht wird, ist Sicherheit. Wenn Sie Sicherheitsfunktionen implementieren möchten, müssen Sie die DAO-Benutzer Objekte und-Gruppen direkt verwenden. Neben der Sicherheit gibt es nur noch einige andere DAO-Features, die nicht von MFC unterstützt werden. Hierzu gehören recordsetklon-und Daten Bank Replikations Features sowie einige späte Ergänzungen zu DAO.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>Eine kurze Übersicht über die Implementierung von DAO und MFC

Das Umwickeln von DAO in MFC vereinfacht die Verwendung von DAO, indem viele der Details verarbeitet werden, sodass Sie sich keine Gedanken mehr über die kleinen Dinge machen müssen. Dies umfasst die Initialisierung von OLE, die Erstellung und Verwaltung der DAO-Objekte (insbesondere die Auflistungs Objekte), die Fehlerüberprüfung und die Bereitstellung einer stark typisierten , einfacheren `BSTR` Schnittstelle (keine Variant oder Argumente). Sie können direkte DAO-Aufrufe durchführen und diese Features weiterhin nutzen. Der gesamte Code muss für alle Objekte `Release` aufgerufen werden, die von Direct DAO-aufrufen erstellt wurden, und es *werden keine der* Schnittstellen Zeiger geändert, von denen MFC intern abhängig sein kann. Ändern Sie z. b. den *m_pDAORecordset* -Member eines geöffneten `CDaoRecordset` Objekts nicht, es sei denn, Sie kennen *alle* internen Auswirkungen. Sie können jedoch die *m_pDAORecordset* -Schnittstelle verwenden, um DAO direkt aufzurufen, um die Fields-Auflistung zu erhalten. In diesem Fall würde das Member *m_pDAORecordset* nicht geändert werden. Wenn Sie mit dem- `Release` Objekt fertig sind, müssen Sie einfach für das Fields-Sammlungsobjekt aufzurufen.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>Beschreibung der Hilfsprogramme zum Vereinfachen von DAO-aufrufen

Die bereitgestellten Hilfsprogramme, um den Aufruf von DAO zu vereinfachen, sind die gleichen Hilfsprogramme, die intern in den MFC-DAO-Datenbankklassen verwendet werden. Diese Hilfsprogramme werden verwendet, um die Rückgabecodes beim Ausführen eines direkten DAO-Aufrufes zu überprüfen, die Debugausgabe zu protokollieren, auf erwartete Fehler zu prüfen und ggf. entsprechende Ausnahmen auszulösen. Es gibt zwei zugrunde liegende Hilfsfunktionen und vier Makros, die einem dieser beiden Hilfsprogramme zugeordnet sind. Die beste Erklärung besteht darin, einfach den Code zu lesen. Weitere Informationen finden Sie unter **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**und **DAO_TRACE** in afxdao. H, um die Makros anzuzeigen, und siehe **afxdaocheck** und **afxdaotrace** in daocore. CPP.

## <a name="using-the-dao-ole-interfaces"></a>Verwenden der DAO-OLE-Schnittstellen

Die OLE-Schnittstellen für jedes Objekt in der DAO-Objekthierarchie werden in der Header Datei dbdaoint definiert. H, der sich im Verzeichnis "\Programme\Microsoft Visual Studio .NET 2003 \ VC7\include" befindet. Diese Schnittstellen stellen Methoden bereit, mit denen Sie die gesamte DAO-Hierarchie bearbeiten können.

Für viele der Methoden in den DAO-Schnittstellen müssen Sie ein `BSTR` -Objekt (eine Zeichenfolge mit Längen Präfix, die in der OLE-Automatisierung verwendet wird) bearbeiten. Das `BSTR` -Objekt ist in der Regel im **Variant** -Datentyp gekapselt. Die MFC- `COleVariant` Klasse selbst erbt vom **Variant** -Datentyp. Abhängig davon, ob Sie das Projekt für ANSI oder Unicode erstellen, geben die DAO-Schnittstellen ANSI `BSTR`oder Unicode s zurück. Zwei Makros, V_BSTR und V_BSTRT, sind nützlich, um sicherzustellen, dass die DAO `BSTR` -Schnittstelle den des erwarteten Typs erhält.

V_BSTR extrahiert den *bstrauval* -Member einer `COleVariant`. Dieses Makro wird normalerweise verwendet, wenn Sie den Inhalt eines `COleVariant` an eine Methode einer DAO-Schnittstelle übergeben müssen. Das folgende Code Fragment zeigt die Deklarationen und die tatsächliche Verwendung für zwei Methoden der DAO daouser-Schnittstelle, die das V_BSTR-Makro nutzen:

```cpp
COleVariant varOldName;
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

// Code to assign pUser to a valid value omitted DAO 3.6 is the final version and it is considered obsolete.User *pUser = NULL;

// These method declarations were taken from DBDAOINT.H
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;
DAO 3.6 is the final version and it is considered obsolete._CHECK(pUser->get_Name(&V_BSTR (&varOldName))); DAO 3.6 is the final version and it is considered obsolete._CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```

Beachten Sie, `VT_BSTRT` dass das `COleVariant` im obigen Konstruktor angegebene Argument sicherstellt, dass ein ANSI `BSTR` in `COleVariant` vorhanden ist, wenn Sie eine ANSI-Version der Anwendung erstellen, `BSTR` und ein Unicode-Element für eine Unicode-Version von. Ihre Anwendung. Dies wird von DAO erwartet.

Das andere Makro, V_BSTRT, extrahiert entweder den ANSI-oder Unicode- *bstrauval* - `COleVariant` Member von, abhängig vom Typ des Builds (ANSI oder Unicode). Der folgende Code veranschaulicht, wie der `BSTR` Wert aus einem `COleVariant` in einen `CString`extrahiert wird:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

Das V_BSTRT-Makro sowie andere Techniken zum Öffnen anderer in `COleVariant`gespeicherter Typen werden im DAOVIEW-Beispiel veranschaulicht. Diese Übersetzung wird insbesondere in der `CCrack::strVARIANT` -Methode durchgeführt. Diese Methode übersetzt, wenn möglich, den Wert eines `COleVariant` in eine Instanz von. `CString`

## <a name="simple-example-of-a-direct-call-to-dao"></a>Einfaches Beispiel für einen direkten Aufrufe von DAO

Situationen können auftreten, wenn die zugrunde liegenden DAO-Auflistungs Objekte aktualisiert werden müssen. Normalerweise sollte dies nicht notwendig sein, aber es ist eine einfache Prozedur, wenn dies erforderlich ist. Ein Beispiel für den Fall, dass eine Auflistung möglicherweise aktualisiert werden muss, ist der Betrieb in einer mehr Benutzerumgebung, in der mehrere Benutzer neue Tabledefs erstellen. In diesem Fall kann es vorkommen, dass die TableDefs-Sammlung veraltet ist. Um die Auflistung zu aktualisieren, müssen Sie einfach die `Refresh` -Methode des jeweiligen Sammlungs Objekts aufzurufen und auf Fehler überprüfen:

```cpp DAO 3.6 is the final version and it is considered obsolete._CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

Beachten Sie, dass alle DAO-Auflistungs Objekt Schnittstellen derzeit nicht dokumentierte Implementierungsdetails der MFC-DAO-Datenbankklassen sind.

## <a name="using-dao-directly-for-dao-security-features"></a>Direktes Verwenden von DAO für DAO-Sicherheits Features

Die MFC-DAO-Datenbankklassen wrappen keine DAO-Sicherheitsfunktionen. Sie müssen Methoden der DAO-Schnittstellen für die Verwendung einiger DAO-Sicherheitsfunktionen aufzurufen. Mit der folgenden Funktion wird die Systemdatenbank festgelegt und anschließend das Kennwort des Benutzers geändert. Diese Funktion ruft drei weitere Funktionen auf, die anschließend definiert werden.

```cpp
void ChangeUserPassword()
{
    // Specify path to the Microsoft Access *// system database
    CString strSystemDB =
        _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

    // Set system database before MFC initilizes DAO
    // NOTE: An MFC module uses only one instance
    // of a DAO database engine object. If you have
    // called a DAO object in your application prior
    // to calling the function below, you must call
    // AfxDaoTerm to destroy the existing database
    // engine object. Otherwise, the database engine
    // object already in use will be reused, and setting
    // a system datbase will have no effect.
    //
    // If you have used a DAO object prior to calling
    // this function it is important that DAO be
    // terminated with AfxDaoTerm since an MFC
    // module only gets one copy of the database engine
    // and that engine will be reused if it hasn't been
    // terminated. In other words, if you do not call
    // AfxDaoTerm and there is currently a database
    // initialized, setting the system database will
    // have no effect.
    SetSystemDB(strSystemDB);

    // User name and password manually added
    // by using Microsoft Access
    CString strUserName = _T("NewUser");
    CString strOldPassword = _T("Password");
    CString strNewPassword = _T("NewPassword");

    // Set default user so that MFC will be able
    // to log in by default using the user name and
    // password from the system database
    SetDefaultUser(strUserName, strOldPassword);

    // Change the password. You should be able to
    // call this function from anywhere in your
    // MFC application
    ChangePassword(strUserName, strOldPassword, strNewPassword);

    // ...
}
```

Die folgenden vier Beispiele veranschaulichen Folgendes:

- Festlegen der DAO-Systemdatenbank (. MDW-Datei).

- Legen Sie den Standardbenutzer und das Kennwort fest.

- Ändern Sie das Kennwort eines Benutzers.

- Ändern Sie das Kennwort eines. MDB-Datei.

### <a name="setting-the-system-database"></a>Festlegen der System Datenbank

Im folgenden finden Sie eine Beispiel Funktion zum Festlegen der Systemdatenbank, die von einer Anwendung verwendet wird. Diese Funktion muss aufgerufen werden, bevor andere DAO-Aufrufe durchgeführt werden.

```cpp
// Set the system database that the
// DAO database engine will use

void SetSystemDB(CString& strSystemMDB)
{
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

    // Initialize DAO for MFC
    AfxDaoInit();
    DAODBEngine* pDBEngine = AfxDaoGetEngine();

    ASSERT(pDBEngine != NULL);

    // Call put_SystemDB method to set the *// system database for DAO engine
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));
}
```

### <a name="setting-the-default-user-and-password"></a>Festlegen des Standard Benutzers und-Kennworts

Verwenden Sie die folgende Funktion, um den Standardbenutzer und das Kennwort für eine Systemdatenbank festzulegen:

```cpp
void SetDefaultUser(CString& strUserName,
    CString& strPassword)
{
    COleVariant varUserName(strUserName, VT_BSTRT);
    COleVariant varPassword(strPassword, VT_BSTRT);

    DAODBEngine* pDBEngine = AfxDaoGetEngine();
    ASSERT(pDBEngine != NULL);

    // Set default user:
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

    // Set default password:
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));
}
```

### <a name="changing-a-users-password"></a>Ändern des Kennworts eines Benutzers

Verwenden Sie die folgende Funktion, um das Kennwort eines Benutzers zu ändern:

```cpp
void ChangePassword(CString &strUserName,
    CString &strOldPassword,
    CString &strNewPassword)
{
    // Create (open) a workspace
    CDaoWorkspace wsp;
    CString strWspName = _T("Temp Workspace");

    wsp.Create(strWspName, strUserName, strOldPassword);
    wsp.Append();

    // Determine how many objects there are *// in the Users collection
    short nUserCount;
    short nCurrentUser;
    DAOUser *pUser = NULL;
    DAOUsers *pUsers = NULL;

    // Side-effect is implicit OLE AddRef()
    // on DAOUser object:
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

    // Side-effect is implicit OLE AddRef()
    // on DAOUsers object
    DAO_CHECK(pUsers->getcount(&nUserCount));

    // Traverse through the list of users
    // and change password for the userid
    // used to create/open the workspace
    for(nCurrentUser = 0; nCurrentUser <nUserCount; nCurrentUser++)
    {
        COleVariant varIndex(nCurrentUser, VT_I2);
        COleVariant varName;

        // Retrieve information for user nCurrentUser
        DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

        // Retrieve name for user nCurrentUser
        DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

        CString strTemp = V_BSTRT(&varName);

        // If there is a match, change the password
        if (strTemp == strUserName)
        {
            COleVariant varOldPwd(strOldPassword, VT_BSTRT);
            COleVariant varNewPwd(strNewPassword, VT_BSTRT);

            DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd),
                V_BSTR(&varNewPwd)));

            TRACE("\t Password is changed\n");
        }
    }
    // Clean up: decrement the usage count
    // on the OLE objects
    pUser->Release();
    pUsers->Release();
    wsp.Close();
}
```

### <a name="changing-the-password-of-an-mdb-file"></a>Ändern des Kennworts einer. MDB-Datei

, Um das Kennwort eines zu ändern. MDB-Datei, verwenden Sie die folgende Funktion:

```cpp
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)
{
    CDaoDatabase db;
    CString strConnect(_T(";pwd="));

    // the database must be opened as exclusive
    // to set a password
    db.Open(pDB, TRUE, FALSE, strConnect + pszOldPassword);

    COleVariant NewPassword(pszNewPassword, VT_BSTRT),
                OldPassword(pszOldPassword, VT_BSTRT);

    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword),
        V_BSTR(&NewPassword)));

    db.Close();
}
```

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
