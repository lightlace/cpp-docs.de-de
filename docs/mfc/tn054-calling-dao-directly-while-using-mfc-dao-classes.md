---
title: "TN054: DAO bei der Verwendung von MFC-DAO-Klassen direkt aufrufen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dao"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (Datenzugriffsobjekte), und MFC"
  - "DAO (Datenzugriffsobjekte), Aufrufen (direkt)"
  - "DAO (Datenzugriffsobjekte), Sicherheit"
  - "MFC [C++], DAO und"
  - "Kennwörter [C++], Aufrufen von DAO"
  - "Sicherheit [MFC]"
  - "Sicherheit [MFC], DAO"
  - "TN054"
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# TN054: DAO bei der Verwendung von MFC-DAO-Klassen direkt aufrufen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt, dass Sie [OLE DB\-Vorlagen](../data/oledb/ole-db-templates.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte verwenden.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
 Wenn Sie die MFC\-DAO\-Datenbankklassen verwendet, kann es Situationen, in denen es erforderlich ist, DAO direkt zu verwenden.  Normalerweise ist dies nicht der Fall, aber MFC verfügt über mehrere Hilfemechanismen erzeugt, um die direkte, DAO\-Aufrufe vereinfachen zu erleichtern, wenn die Verwendung der MFC\-Klassen mit direkten DAO\-Aufrufen kombinierte.  Die Durchführung von direkten DAO\-Aufrufen an Methoden eines MFC\-verwalteten DAO\-Objekts sollte nur einige Codezeilen erforderlich.  Wenn Sie DAO\-Objekte erstellen und verwenden, die MFC *nicht* verwaltet werden, müssen Sie weitere Arbeit etwas ausführen, indem Sie tatsächlich **Version** für das Objekt aufgerufen.  Dieser technische Hinweis erläutert, als Sie DAO direkt aufrufen sollten, was die MFC\-Hilfen ausführen können, um Ihnen helfen und die Schnittstellen DAO OLE verwendet.  Schließlich stellt dieser Hinweis einige Beispielfunktionen, die wie DAO direkt für DAO\-Sicherheitsmerkmale anzeigen, aufgerufen.  
  
## Wann Sie direkte DAO\-Aufrufe macht  
 Die häufigsten Situationen zur Durchführung von direkten DAO\-Aufrufen treten auf, wenn Auflistungen aktualisiert werden müssen, oder wenn Sie die Funktionen implementieren, die MFC nicht umbrochen werden.  Die wichtigste Funktion, die MFC nicht verfügbar gemacht wird, ist Sicherheit.  Wenn Sie Sicherheit implementieren möchten, müssen Sie die DAO\-Benutzer\-undGruppenobjekte direkt verwenden.  Neben Sicherheit ist nur mehrere andere DAO\-Funktionen, die MFC nicht unterstützt werden.  Diese schließen Recordsetklonen\- und \-Datenbankreplikationsfunktionen sowie einige späte Hinzufügungen zu DAO ein.  
  
## Eine kurze Übersicht von DAO\- und MFC\-Implementierung  
 Umschließen MFC von DAO macht mit DAO erleichtert, indem er viele der Details behandelt, müssen Sie sich um Kleinigkeiten zu kümmern.  Dies schließt die Initialisierung von OLE, Erstellung und Verwaltung der DAO\-Objekte \(besonders die Auflistungsobjekten\), der Fehlerüberprüfung und der Lieferung einer stark typisierten, einfachere Schnittstelle ein \(kein **VARIANT** oder `BSTR`\-Argumente\).  Sie können direkte DAO\-Aufrufe ausführen und die Funktionen noch nutzen.  der gesamte Code muss erreichen, **Version** für alle Objekte aus, die durch direkte DAO\-Aufrufe und alle von Schnittstellenzeigern *nicht* ändern erstellt werden, dass MFC intern möglicherweise angezeigt wird.  Ändern Sie beispielsweise **m\_pDAORecordset** nicht den Member eines offenen `CDaoRecordset`\-Objekts, es sei denn, Sie *alle* internen Klaren sein.  Sie können die **m\_pDAORecordset**\-Schnittstelle jedoch verwenden, um direkt aufzurufen DAO, um der Framesauflistung abzurufen.  In diesem Fall würde der **m\_pDAORecordset**\-Member nicht geändert.  Sie müssen auf dem Feldauflistungsobjekt einfach **Version** aufrufen, wenn Sie mit dem Objekt beendet werden.  
  
## Beschreibung von Ihnen, mit der DAO\-Aufrufen zu vereinfachen  
 Zudem trägt, die bereitgestellt werden, um das Aufrufen von DAO einfacher zu machen, sind die gleichen erleichtert, die intern in den MFC\-DAO\-Datenbankklassen verwendet werden.  Hilfen Diese werden verwendet, um der Rückgabecodes zu überprüfen, um einen direkten DAO\-Aufruf macht und protokolliert, Debugausgabe, überprüfen erwartete Fehler ggf. entsprechende, und lösen Ausnahmen aus.  Es gibt zwei zugrunde liegende Hilfsfunktionen und vier Makros, die einer dieser beiden Hilfen zuordnen.  Die beste Erläuterung wird, den Code einfach zu lesen sein.  Siehe **DAO\_CHECK**, **DAO\_CHECK\_ERROR**, **DAO\_CHECK\_MEM** und **DAO\_TRACE** in AFXDAO.H, um die Makros zu finden, und finden Sie unter **AfxDaoCheck** und **AfxDaoTrace** in DAOCORE.CPP.  
  
## Mithilfe der Schnittstellen DAO OLE  
 Die OLE\-Schnittstellen für jedes Objekt in der DAO\-Objekthierarchie werden in der Headerdatei DBDAOINT.H definiert, die sich im Verzeichnis \\Programme\\Microsoft Visual Studio .NET 2003\\VC7\\include befindet.  Diese Schnittstellen stellen Methoden bereit, die es Ihnen ermöglichen, die gesamte DAO\-Hierarchie zu bearbeiten.  
  
 Viele der Methoden in den DAO\-Schnittstellen, müssen Sie ein `BSTR`\-Objekt \(eine Länge\-vorangestellte Zeichenfolge verwendet in der OLE\-Automatisierung\) bearbeiten.  Das `BSTR`\-Objekt wird normalerweise innerhalb des **VARIANT** Datentyps gekapselt.  Die abgeleitete MFC\-Klasse `COleVariant` selbst erbt vom Datentyp **VARIANT**.  Je nachdem, ob Sie das Projekt bei ANSI oder Unicode erstellen, geben die DAO\-Schnittstellen ANSI oder Unicode `BSTR`s zurück.  Zwei Makros, **V\_BSTR** und **V\_BSTRT**, sind zum Gewährleisten nützlich, dass die DAO\-Schnittstelle `BSTR` des erwarteten Typs abrufen.  
  
 **V\_BSTR** Gibt den **bstrVal**\-Member von `COleVariant`.  Dieses Makro wird normalerweise verwendet, wenn Sie den Inhalt von `COleVariant` auf eine Methode einer DAO\-Schnittstelle übergeben müssen.  Im folgenden Codefragment zeigt die Deklaration und tatsächliche Verwendung für zwei Methoden der Schnittstelle DAOUser DAO an, die das **V\_BSTR**\-Makro verwenden:  
  
```  
COleVariant varOldName;  
COleVariant varNewName( _T("NewUser"), VT_BSTRT );  
  
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
  
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
  
DAO_CHECK( pUser->get_Name( &V_BSTR ( &varOldName ) ));  
DAO_CHECK( pUser->put_Name( V_BSTR ( &varNewName ) ));  
```  
  
 Beachten Sie, dass das Argument `VT_BSTRT`, das im obigen `COleVariant`\-Konstruktor angegeben wird, wird sichergestellt, dass es ANSI `BSTR` in `COleVariant` gibt, wenn Sie eine ANSI\-Version der Anwendung und Unicode für einen `BSTR` eine Unicode\-Version der Anwendung erstellen.  Dies ist, was DAO erwartet.  
  
 Das andere Makro, **V\_BSTRT**, extrahiert entweder ANSI oder Unicode\- **bstrVal**\-Member von `COleVariant` je nach Art des Builds \(ANSI oder Unicode\).  Der folgende Code zeigt, wie Sie den `BSTR`\-Wert von `COleVariant` in `CString` abstrahiert:  
  
```  
COleVariant varName( _T( "MyName" ), VT_BSTRT );  
CString str = V_BSTRT( &varName );  
```  
  
 Das **V\_BSTRT**\-Makro, zusammen mit anderen Verfahren, andere Typen zu öffnen, die in `COleVariant` gespeichert werden, wird im DAOVIEW\-Beispiel veranschaulicht.  Insbesondere wird diese Verschiebung in der **CCrack::strVARIANT**\-Methode ausgeführt.  Diese Methode, übersetzt nach Möglichkeit den Wert von `COleVariant` in eine Instanz von `CString`.  
  
## Einfaches Beispiel eines direkten Aufruf zu DAO  
 Situationen können möglicherweise, wenn es erforderlich ist, die zugrunde liegenden DAO\-Auflistungsobjekte zu aktualisieren.  Normalerweise sollte dies nicht notwendig sein, es ist eine einfache Prozedur, wenn es erforderlich ist.  Ein Beispiel, als Auflistung möglicherweise aktualisiert werden muss, ist beim mit in einer Mehrbenutzerumgebung mit den Benutzern, die neue Tabledefs erstellen.  In diesem Fall kann die Tabledef\-Auflistung veraltet.  Wenn Sie die Auflistung zu aktualisieren, müssen Sie die **Aktualisieren**\-Methode des bestimmten Auflistungsobjekts aufrufen und für Fehler überprüfen:  
  
```  
DAO_CHECK( pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh( ) );  
```  
  
 Beachten Sie, dass nur alle DAO\-Auflistungsobjektschnittstellen nicht dokumentierten Implementierungsdetails der MFC\-DAO\-Datenbankklassen sind.  
  
## Mit DAO direkt für DAO\-Sicherheitsmerkmale  
 Die MFC\-DAO\-Datenbankklassen binden nicht DAO\-Sicherheitsmerkmale ein.  Sie müssen Methoden von DAO\-Schnittstellen aufrufen, um einige DAO\-Sicherheitsmerkmale zu verwenden.  Die folgende Funktion legt die Systemdatenbank fest und ändert dann das Kennwort des Benutzers.  Diese Funktion ruft drei weitere Funktionen, die anschließend definiert werden.  
  
```  
void ChangeUserPassword( )  
{  
   // Specify path to the Microsoft Access  
   // system database  
   CString strSystemDB =   
     _T( "c:\\Program Files\\MSOffice\\access\\System.mdw" );  
  
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
   // have no affect.  
  
   SetSystemDB( strSystemDB );  
  
   // User name and password manually added  
   // by using Microsoft Access  
   CString strUserName = _T( "NewUser" );  
   CString strOldPassword = _T( "Password" );  
   CString strNewPassword = _T( "NewPassword" );  
  
   // Set default user so that MFC will be able  
   // to log in by default using the user name and   
   // password from the system database  
   SetDefaultUser( strUserName, strOldPassword );  
  
   // Change the password. You should be able to  
   // call this function from anywhere in your   
   // MFC application  
   ChangePassword( strUserName, strOldPassword,   
                   strNewPassword );  
  
   .  
   .  
   .  
  
}  
```  
  
 Die folgenden vier Beispiele zeigen, wie:  
  
-   Legen Sie die System DAO\-Datenbank fest \(.MDW\-Datei\).  
  
-   Legen Sie den Standardbenutzer und Kennwort fest.  
  
-   Ändern Sie das Kennwort eines Benutzers.  
  
-   Legen Sie als Kennwort eine MDB\-Datei.  
  
### Festlegen der Systemdatenbank  
 Unten ist eine Beispielfunktion, um die Systemdatenbank festzulegen, die von einer Anwendung verwendet wird.  Diese Funktion muss aufgerufen werden, bevor alle anderen DAO\-Aufrufe gemacht werden.  
  
```  
// Set the system database that the   
// DAO database engine will use  
  
void SetSystemDB( CString & strSystemMDB )  
{  
   COleVariant varSystemDB( strSystemMDB, VT_BSTRT );  
  
   // Initialize DAO for MFC  
   AfxDaoInit( );  
   DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  
   ASSERT( pDBEngine != NULL );  
  
   // Call put_SystemDB method to set the   
   // system database for DAO engine  
   DAO_CHECK( pDBEngine->put_SystemDB( varSystemDB.bstrVal ) );  
}  
```  
  
### Festlegen des Standard\-Benutzers und des Kennworts  
 Um den Standardbenutzer und Kennwort für eine Systemdatenbank festzulegen, verwenden Sie die folgende Funktion:  
  
```  
void SetDefaultUser(CString & strUserName, CString & strPassword)  
{  
  COleVariant varUserName( strUserName, VT_BSTRT );  
  COleVariant varPassword( strPassword, VT_BSTRT );  
  
  DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  ASSERT( pDBEngine != NULL );  
  
  // Set default user:  
  DAO_CHECK( pDBEngine->put_DefaultUser( varUserName.bstrVal ) );  
  
  // Set default password:  
  DAO_CHECK( pDBEngine->put_DefaultPassword( varPassword.bstrVal ) );  
}  
```  
  
### Ändern eines Kennworts des Benutzers  
 Um ein Kennwort des Benutzers zu ändern, verwenden Sie die folgende Funktion:  
  
```  
void ChangePassword( CString &strUserName,   
                     CString &strOldPassword,   
                     CString &strNewPassword )  
{  
   // Create (open) a workspace  
   CDaoWorkspace wsp;  
   CString strWspName = _T( "Temp Workspace" );  
  
   wsp.Create( strWspName, strUserName,  
               strOldPassword );  
   wsp.Append( );  
  
   // Determine how many objects there are  
   // in the Users collection  
   short nUserCount;  
   short nCurrentUser;  
   DAOUser *pUser  = NULL;  
   DAOUsers *pUsers = NULL;  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUser object:  
   DAO_CHECK( wsp.m_pDAOWorkspace->get_Users( &pUsers ) );  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUsers object  
    DAO_CHECK( pUsers->get_Count( &nUserCount ) );  
  
   // Traverse through the list of users   
   // and change password for the userid  
   // used to create/open the workspace  
   for( nCurrentUser = 0; nCurrentUser < nUserCount;  
        nCurrentUser++ )  
   {  
       COleVariant varIndex( nCurrentUser, VT_I2 );  
       COleVariant varName;  
  
       // Retrieve information for user nCurrentUser  
       DAO_CHECK( pUsers->get_Item( varIndex, &pUser ) );  
  
       // Retrieve name for user nCurrentUser  
       DAO_CHECK( pUser->get_Name( &V_BSTR( &varName ) ) );  
  
       CString strTemp = V_BSTRT( &varName );  
  
       // If there is a match, change the password  
       if( strTemp == strUserName )  
       {  
           COleVariant varOldPwd( strOldPassword,   
                                  VT_BSTRT );  
           COleVariant varNewPwd( strNewPassword,   
                                  VT_BSTRT );  
  
           DAO_CHECK( pUser->NewPassword( V_BSTR( &varOldPwd ),  
                      V_BSTR( &varNewPwd ) ) );  
  
           TRACE( "\t Password is changed\n" );  
       }  
   }  
  
   // Clean up: decrement the usage count  
   // on the OLE objects  
   pUser->Release( );  
   pUsers->Release( );  
  
   wsp.Close( );  
}  
```  
  
### Ändern des Kennworts eine MDB\-Datei  
 Um das Kennwort eine MDB\-Datei zu ändern, verwenden Sie die folgende Funktion:  
  
```  
void SetDBPassword( LPCTSTR pDB, LPCTSTR pszOldPassword, LPCTSTR pszNewPassword )  
{  
   CDaoDatabase db;  
   CString strConnect( _T( ";pwd=" ) );  
  
   // the database must be opened as exclusive  
   // to set a password  
   db.Open( pDB, TRUE, FALSE,   
            strConnect + pszOldPassword );  
  
   COleVariant NewPassword( pszNewPassword, VT_BSTRT ),  
               OldPassword( pszOldPassword, VT_BSTRT );  
  
   DAO_CHECK( db.m_pDAODatabase->NewPassword( V_BSTR( &OldPassword ),  
              V_BSTR( &NewPassword ) ) );  
  
   db.Close();  
}  
```  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)