---
title: 'TN054: DAO bei der Verwendung von MFC-DAO-Klassen direkt aufrufen. | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dao
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b53eaa618f06ab7644edf454e097286a3ce3cc71
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393112"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: DAO bei der Verwendung von MFC-DAO-Klassen direkt aufrufen

> [!NOTE]
> Die Visual C++-Umgebung und den Assistenten unterstützen DAO keine (obwohl die DAO-Klassen enthalten sind, und Sie können diese weiterhin verwenden). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO Verwaltung bereits vorhandener Anwendungen verwenden.

Wenn Sie die MFC-DAO-Datenbankklassen verwenden zu können, gibt es möglicherweise Situationen, in denen es erforderlich, DAO direkt zu verwenden. Klicken Sie in der Regel wird dies nicht der Fall sein, aber MFC verfügt über einige Mechanismen Helper Erleichterung und direkte DAO-Aufrufe einfach beim Kombinieren der Verwendung der MFC-Klassen mit direkten Aufrufen von DAO bereitgestellt. Direkte DAO sollten Aufrufe der Methoden eines verwaltete MFC DAO-Objekts nur ein paar Zeilen Code erfordert. Wenn Sie benötigen zum Erstellen und Verwenden von DAO-Objekte, die *nicht* von MFC verwaltet, müssen Sie dazu, dass ein wenig mehr Aufwand tatsächlich Aufrufen `Release` für das Objekt. Diese technische Hinweis wird erläutert, wenn Sie möchten möglicherweise DAO direkt aufrufen, was die MFC-Hilfsprogramme tun können, damit Sie und wie Sie die DAO-OLE-Schnittstellen verwenden. Schließlich stellt dieser Hinweis Einige Beispielfunktionen, die zeigt, wie zum Aufrufen von DAO direkt für die DAO-Sicherheitsfeatures bereit.

## <a name="when-to-make-direct-dao-calls"></a>Wenn für Direct DAO-Aufrufe

Die gängigsten Überwachungssituationen darstellen, zum Ausführen von direkten Aufrufen von DAO auftreten, wenn es sich bei Auflistungen müssen aktualisiert werden, oder wenn Sie Funktionen von MFC nicht umschlossen implementieren. Das wichtigste Feature nicht verfügbar gemacht, von MFC ist Sicherheit. Wenn Sie die Sicherheitsfunktionen zu implementieren möchten, müssen Sie die DAO-Benutzer und Gruppen-Objekte direkt verwenden. Neben Sicherheit es gibt nur wenige andere DAO-Funktionen von MFC nicht unterstützt. Dazu gehören das Recordset zu klonen und Datenbank-Replikationsfunktionen sowie einige spät Ergänzungen zu DAO.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>Eine kurze Übersicht über DAO und MFC Implementierung

Umschließen der MFC DAO-kann mit DAO einfacher durch das behandeln viele der Details müssen nicht über die kleinen Dinge Gedanken machen. Dies schließt die Initialisierung von OLE, die Erstellung und Verwaltung der DAO-Objekte (insbesondere die Auflistungsobjekte), Fehler und Bereitstellen einer stark typisierten, einfacheren Benutzeroberfläche (keine **VARIANT** oder `BSTR` (Argumente). Sie können direkte Aufrufen von DAO und weiterhin diese Features nutzen. Ihr Code muss nur der Aufruf ist `Release` Ruft für alle Objekte, die durch direkte DAO erstellt und *nicht* ändern Sie den Schnittstellenzeiger, der MFC intern basieren kann. Ändern Sie z. B. nicht die *M_pDAORecordset* Member eines geöffneten `CDaoRecordset` Objekt, es sei denn, Sie verstehen, *alle* die interne Auswirkungen. Sie können jedoch mithilfe der *M_pDAORecordset* Schnittstelle zum Aufrufen von DAO direkt, um die feldauflistung zu erhalten. In diesem Fall die *M_pDAORecordset* Element wird nicht geändert werden. Sie müssen einfach aufrufen `Release` auf das Auflistungsobjekt Felder, wenn Sie mit dem Objekt fertig sind.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>Beschreibung der Hilfsprogramme zu DAO aufruft einfacher

Die Hilfsprogramme, die bereitgestellt werden, um Aufrufen von DAO ist einfacher zu machen sind die gleichen Hilfsprogramme, die intern in die MFC-DAO-Datenbankklassen verwendet werden. Diese Hilfsprogramme werden verwendet, um der Rückgabecodes zu überprüfen, wenn Sie einen direkten Aufruf der DAO, vornehmen, Debugausgaben, Protokollierung, erwartete Fehler überprüfen und entsprechende Ausnahmen auslösen, falls erforderlich. Es gibt zwei zugrunde liegenden Hilfsfunktionen und vier Makros, die einer dieser beiden Hilfsfunktionen zugeordnet. Die beste Erklärung wäre, die den Code einfach zu lesen. Finden Sie unter **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**, und **DAO_TRACE** in AFXDAO. H, um die Makros, und **AfxDaoCheck** und **AfxDaoTrace** in DAOCORE. CPP.

## <a name="using-the-dao-ole-interfaces"></a>Mithilfe von DAO-OLE-Schnittstellen

Die OLE-Schnittstellen für jedes Objekt in der Objekthierarchie DAO-werden in der Headerdatei DBDAOINT definiert. H, die sich im Verzeichnis \Programme\Microsoft Visual Studio .NET 2003\VC7\include befindet. Diese Schnittstellen bieten Methoden, mit die Sie die gesamte DAO-Hierarchie bearbeiten können.

Für viele der Methoden in den DAO-Schnittstellen, benötigen Sie zum Bearbeiten einer `BSTR` Objekt (ein Längenpräfix Zeichenfolge, die in der OLE-Automatisierung verwendet). Die `BSTR` Objekt in der Regel ist Teil der **VARIANT** -Datentyp. Die MFC-Klasse `COleVariant` selbst erbt von der **VARIANT** -Datentyp. Je nachdem, ob Sie Ihr Projekt für ANSI- oder Unicode-erstellen, die DAO-Schnittstellen gibt ANSI- oder Unicode- `BSTR`s. Zwei Makros V_BSTR und V_BSTRT, eignen sich für sicherstellt, dass die DAO-Schnittstelle ruft die `BSTR` den erwarteten Typ.

V_BSTR extrahiert die *BstrVal* Mitglied einer `COleVariant`. Dieses Makro wird in der Regel verwendet, wenn Sie den Inhalt des übergeben müssen eine `COleVariant` an eine Methode einer DAO-Schnittstelle. Das folgende Codefragment zeigt die Deklarationen und die tatsächliche Verwendung für zwei Methoden der DAO-DAOUser-Schnittstelle, die das Makro V_BSTR nutzen:

```cpp
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

Beachten Sie, dass die `VT_BSTRT` angegebene Argument in der `COleVariant` Konstruktor oben wird sichergestellt, dass es wird ein ANSI `BSTR` in die `COleVariant` Wenn Sie eine ANSI-Version Ihrer Anwendung und ein Unicode-erstellen `BSTR` für eine Unicode-Version von Ihre Anwendung. Dies ist, was DAO erwartet.

Extrahiert das andere Makro V_BSTRT, entweder eine ANSI- oder Unicode *BstrVal* Mitglied `COleVariant` je nach Art des Builds (ANSI oder Unicode). Der folgende Code zeigt, wie Sie extrahieren die `BSTR` Wert aus einer `COleVariant` in einer `CString`:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

Das Makro V_BSTRT, zusammen mit anderen Techniken zum Öffnen von anderen Dateitypen, die in gespeichert werden `COleVariant`, wird im Beispiel DAOVIEW veranschaulicht. Diese Übersetzung erfolgt insbesondere in den `CCrack::strVARIANT` Methode. Diese Methode, wenn möglich, übersetzt den Wert von einem `COleVariant` in eine Instanz von `CString`.

## <a name="simple-example-of-a-direct-call-to-dao"></a>Einfaches Beispiel für einen direkten Aufruf nach DAO

Bei Bedarf die zugrunde liegenden Objekte der DAO-Sammlung zu aktualisieren, können Situationen auftreten. In der Regel Dies sollte nicht erforderlich sein, aber es ist ein einfaches Verfahren, wenn es erforderlich ist. Ein Beispiel an, wenn eine Auflistung benötigen möglicherweise aktualisiert werden ist während des Betriebs in einer mehrbenutzerumgebung mit mehreren Benutzern neue Tabledefs erstellen. In diesem Fall kann Ihr Tabledefs-Auflistung veralten. Um der Auflistung zu aktualisieren, müssen Sie lediglich Aufrufen der `Refresh` Methode des bestimmten-Objekt, und prüfen auf Fehler:

```cpp
DAO_CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

Beachten Sie, dass derzeit alle DAO-Auflistungsschnittstellen nicht dokumentierten Implementierungsdetails von den MFC-DAO-Datenbankklassen.

## <a name="using-dao-directly-for-dao-security-features"></a>Mithilfe von DAO direkt für DAO-Sicherheitsfunktionen

Die MFC-DAO-Datenbankklassen Zeilenumbruch DAO-Sicherheitsfunktionen kein. Sie müssen die Methoden der DAO-Schnittstellen verwenden einige Sicherheitsfunktionen DAO aufrufen. Die folgende Funktion wird die Systemdatenbank und anschließend das Kennwort des Benutzers. Diese Funktion ruft drei andere Funktionen, die anschließend definiert sind.

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

Die folgenden vier Beispielen wird gezeigt, wie Sie:

- Stellen Sie die System-DAO-Datenbank (. MDW-Datei).

- Legen Sie den Standard-Benutzer und das Kennwort ein.

- Ändern Sie das Kennwort eines Benutzers.

- Ändern Sie das Kennwort ein. MDB-Datei.

### <a name="setting-the-system-database"></a>Die Systemdatenbank festlegen

Es folgt eine Beispiel-Funktion für die Systemdatenbank zu aktivieren, die von einer Anwendung verwendet werden. Diese Funktion muss aufgerufen werden, bevor alle anderen DAO-Aufrufe durchgeführt werden.

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

### <a name="setting-the-default-user-and-password"></a>Festlegen der Standard-Benutzer und Kennwort

Um den Standard-Benutzer und das Kennwort für eine Systemdatenbank zu festzulegen, verwenden Sie die folgende Funktion:

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

### <a name="changing-a-users-password"></a>Ändern das Kennwort eines Benutzers

Um das Kennwort eines Benutzers zu ändern, verwenden Sie die folgende Funktion:

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

### <a name="changing-the-password-of-an-mdb-file"></a>Ändern des Kennworts für ein. MDB-Datei

So ändern Sie das Kennwort ein. MDB-Datei, verwenden Sie die folgende Funktion:

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
