---
title: CDaoException Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoException
dev_langs:
- C++
helpviewer_keywords:
- errors [C++], DAO
- CDaoException class
- DAO (Data Access Objects), exceptions
- exceptions, in MFC DAO classes
- Errors collection, DAO
- collections, DAO errors
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d1cb1c6dbe50d383981af03cc97d1977be12a5f6
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoexception-class"></a>CDaoException-Klasse
Stellt eine Ausnahmebedingung dar, die von MFC-Datenbankklassen in Bezug auf Datenzugriffsobjekte (DAOs) ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|Erstellt ein `CDaoException`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException:: GetErrorCount](#geterrorcount)|Gibt die Anzahl der Fehler in das Datenbankmodul Errors-Auflistung zurück.|  
|[CDaoException:: GetErrorInfo](#geterrorinfo)|Gibt Informationen zu einem bestimmten Fehler-Objekt in der Errors-Auflistung zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|Enthält einen erweiterter Fehlercode für alle Fehler in den MFC-DAO-Klassen.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Ein Zeiger auf eine [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) -Objekt, das Informationen über eine DAO Error-Objekt enthält.|  
|[CDaoException::m_scode](#m_scode)|Die [SCODE](#m_scode) Wert, mit dem Fehler zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse enthält öffentliche Datenmember, die Sie verwenden können, um die Ursache der Ausnahme zu bestimmen. `CDaoException`Objekte werden erstellt und von Memberfunktionen von den DAO-Datenbankklassen ausgelöst.  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können immer noch Zugriff auf ODBC-Datenquellen mit DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die ODBC-basierten MFC-Klassen. DAO-basierte Klassen können Daten, einschließlich der über ODBC-Treiber, über ihre eigenen Datenbank-Engine zugreifen. DAO-basierte Klassen unterstützen auch Vorgänge (Data Definition Language, Datendefinitionssprache), z. B. das Hinzufügen von Tabellen über die Klassen ohne DAO direkt aufrufen. Informationen zu Ausnahmen, die von der ODBC-Klassen ausgelöst werden, finden Sie unter [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Sie erreichen Exception-Objekte innerhalb des Bereichs einer [CATCH](../../mfc/reference/exception-processing.md#catch) Ausdruck. Sie können auch Auslösen `CDaoException` Objekte aus Ihrem eigenen Code mit der [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) globale Funktion.  
  
 In MFC werden alle DAO-Fehler als Ausnahmen vom Typ ausgedrückt `CDaoException`. Wenn Sie eine Ausnahme dieses Typs abfangen, können Sie `CDaoException` Memberfunktionen zum Abrufen von Informationen über alle DAO-Fehler-Objekte, die in die Datenbank-Engine Errors-Auflistung gespeichert. Sobald ein Fehler auftritt, werden eine oder mehrere Error-Objekte in der Errors-Auflistung platziert. (Normalerweise die Auflistung enthält nur ein Fehlerobjekt, wenn Sie eine ODBC-Datenquelle verwenden, sind Sie wahrscheinlich mehrere Error-Objekte werden.) Wenn eine andere DAO-Operation einen Fehler generiert, die Errors-Auflistung deaktiviert ist, und das neue Fehlerobjekt befindet sich in der Errors-Auflistung. DAO-Operationen, die keinen Fehler generieren haben keine Auswirkung auf die Errors-Auflistung.  
  
 DAO-Fehlercodes finden Sie in der Datei DAOERR. H. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriff" in der DAO-Hilfe.  
  
 Weitere Informationen zur Behandlung von Ausnahmen in allgemeinen oder etwa `CDaoException` von Objekten finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md). Der zweite Artikel enthält Beispielcode, der Ausnahmebehandlung in DAO veranschaulicht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="a-namecdaoexceptiona--cdaoexceptioncdaoexception"></a><a name="cdaoexception"></a>CDaoException::CDaoException  
 Erstellt ein `CDaoException`-Objekt.  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>Hinweise  
 Normalerweise erstellt das Framework Ausnahmeobjekte, wenn der Code eine Ausnahme auslöst. Sie müssen nur selten explizit ein Exception-Objekt zu erstellen. Wenn Sie lösen möchten eine `CDaoException` aus Ihrem eigenen Code rufen Sie die globale Funktion [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).  
  
 Sie möchten jedoch explizit ein Exception-Objekt erstellen, wenn Sie direkte DAO über die DAO-Schnittstellenzeiger aufrufen, die MFC-Klassen kapseln. In diesem Fall müssen Sie zum Abrufen von Fehlerinformationen von DAO. Angenommen Sie, ein Fehler in DAO tritt auf, wenn Sie eine DAO-Methode über die Schnittstelle DAODatabases eines Arbeitsbereichs Databases-Auflistung aufrufen.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>Zum Abrufen der Fehlerinformationen DAO  
  
1.  Konstruieren Sie ein `CDaoException`-Objekt.  
  
2.  Rufen Sie des Ausnahmeobjekts [GetErrorCount](#geterrorcount) Member-Funktion, um zu bestimmen, wie viele Fehlerobjekte in der Datenbank-Engine Errors-Auflistung sind. (Normalerweise nur ein, wenn Sie eine ODBC-Datenquelle verwenden.)  
  
3.  Rufen Sie des Ausnahmeobjekts [GetErrorInfo](#geterrorinfo) Member-Funktion zum Abrufen einer bestimmten Error-Objekt zu einem Zeitpunkt nach Index in der Auflistung, über das Ausnahmeobjekt. Stellen Sie sich das Exception-Objekt als Proxy für ein DAO-Fehlerobjekt.  
  
4.  Überprüfen Sie die aktuelle [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) zu strukturieren, dass `GetErrorInfo` gibt in der [M_pErrorInfo](#m_perrorinfo) -Datenmember. Ihre Mitglieder bieten Informationen zu den DAO-Fehler.  
  
5.  Wiederholen Sie die Schritte 3 und 4 für weitere Fehlerobjekte bei Bedarf im Fall einer ODBC-Datenquelle.  
  
6.  Wenn Sie das Exception-Objekt auf dem Heap erstellt haben, löschen Sie ihn mit der **löschen** Operator, wenn Sie fertig sind.  
  
 Weitere Informationen zur Behandlung von Fehlern in den MFC-DAO-Klassen finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="a-namegeterrorcounta--cdaoexceptiongeterrorcount"></a><a name="geterrorcount"></a>CDaoException:: GetErrorCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von DAO Error-Objekte in der Datenbank-Engine Errors-Auflistung.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Fehler DAO-in die Datenbank-Engine Errors-Auflistung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen sind nützlich zum Durchlaufen der Auflistung Fehler jeweils eine oder mehrere DAO Error-Objekte in der Auflistung abgerufen. Um ein Error-Objekt nach Index oder DAO-Fehlernummer abzurufen, rufen Sie die [GetErrorInfo](#geterrorinfo) Member-Funktion.  
  
> [!NOTE]
>  Normalerweise liegt nur ein Error-Objekt in der Errors-Auflistung. Wenn Sie eine ODBC-Datenquelle arbeiten, jedoch gibt es möglicherweise mehrere.  
  
##  <a name="a-namegeterrorinfoa--cdaoexceptiongeterrorinfo"></a><a name="geterrorinfo"></a>CDaoException:: GetErrorInfo  
 Gibt Informationen zu einem bestimmten Fehler-Objekt in der Errors-Auflistung zurück.  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index der Fehlerinformationen in die Datenbank-Engine-Errors-Auflistung für die Suche nach Index.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die folgenden Arten von Informationen über die Ausnahme zu erhalten:  
  
-   Fehlercode  
  
-   Quelle  
  
-   Beschreibung  
  
-   Hilfedatei  
  
-   Hilfekontext  
  
 `GetErrorInfo`Speichert die Informationen in des Ausnahmeobjekts `m_pErrorInfo` -Datenmember. Eine kurze Beschreibung der zurückgegebenen Informationen, finden Sie unter [M_pErrorInfo](#m_perrorinfo). Wenn Sie eine Ausnahme vom Typ `CDaoException` ausgelöste MFC die `m_pErrorInfo` Member bereits ausgefüllt. DAO direkt aufgerufen werden soll, rufen Sie des Ausnahmeobjekts `GetErrorInfo` Memberfunktion selbst füllen `m_pErrorInfo`. Eine ausführlichere Beschreibung finden Sie in der [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Struktur.  
  
 Informationen über DAO-Ausnahmen und Beispielcode finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="a-namemnafxdaoerrora--cdaoexceptionmnafxdaoerror"></a><a name="m_nafxdaoerror"></a>CDaoException::m_nAfxDaoError  
 Enthält eine erweiterten Fehlercode MFC.  
  
### <a name="remarks"></a>Hinweise  
 In Fällen, in denen eine bestimmte Komponente der MFC-DAO-Klassen bezieht, ist, dieser Code angegeben.  
  
 Dabei sind folgende Werte möglich:  
  
- **NO_AFX_DAO_ERROR** letzte Vorgang führten nicht in einer MFC erweiterter Fehler. Allerdings der Vorgang konnte erzeugen, andere Fehler von DAO oder OLE, also Sie checken [M_pErrorInfo](#m_perrorinfo) und möglicherweise [M_scode](#m_scode).  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC konnte das Microsoft Jet-Datenbankmodul nicht initialisieren. OLE kann konnte nicht initialisiert werden oder wurden zum Erstellen einer Instanz des Objekts DAO-Datenbank-Engine nicht möglich. Diese Probleme wird in der Regel eine fehlerhafte Installation von DAO oder OLE empfohlen.  
  
- **AFX_DAO_ERROR_DFX_BIND** eine Adresse in einem Funktionsaufruf für DAO-Datensatz Feld Datensatzfeldaustausch (DFX) ist nicht vorhanden oder ist ungültig (die Adresse nicht verwendet, um Daten zu binden). Sie haben eine ungültige Adresse können in einem DFX-Aufruf übergeben, oder die Adresse möglicherweise ungültig geworden ist zwischen DFX-Operationen.  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN** Sie haben versucht, ein Recordset basierend auf einer Querydef oder Tabledef-Objekts, die nicht im geöffneten Zustand zu öffnen.  
  
##  <a name="a-namemperrorinfoa--cdaoexceptionmperrorinfo"></a><a name="m_perrorinfo"></a>CDaoException::m_pErrorInfo  
 Enthält einen Zeiger auf eine `CDaoErrorInfo` -Struktur, die Informationen für das Fehlerobjekt DAO, die Sie zuletzt abgerufen haben bereitstellt, durch Aufrufen von [GetErrorInfo](#geterrorinfo).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt enthält die folgende Informationen:  
  
|CDaoErrorInfo-Element|Information|Bedeutung|  
|--------------------------|-----------------|-------------|  
|**m_lErrorCode**|Fehlercode|DAO-Fehlercode:|  
|`m_strSource`|Quelle|Der Name des Objekts oder der Anwendung, die ursprünglich den Fehler generiert hat|  
|`m_strDescription`|Beschreibung|Eine beschreibende Zeichenfolge, die dem Fehler zugeordnete|  
|`m_strHelpFile`|Hilfe-Datei|Ein Pfad zu einer Windows-Hilfedatei in der der Benutzer Informationen zu diesem Problem erhalten|  
|**m_lHelpContext**|Hilfekontext|Die Kontext-ID für ein Thema in der Hilfedatei von DAO|  
  
 Ausführliche Informationen zu den Informationen in der `CDaoErrorInfo` Objekt, finden Sie unter der [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Struktur.  
  
##  <a name="a-namemscodea--cdaoexceptionmscode"></a><a name="m_scode"></a>CDaoException::m_scode  
 Einen Wert vom Typ enthält `SCODE` , die den Fehler beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein OLE-Code. Sie benötigen nur selten, diesen Wert zu verwenden, da in fast allen Fällen spezifischere MFC oder DAO-Fehlerinformationen in der anderen verfügbar ist `CDaoException` Datenmember.  
  
 Informationen zu `SCODE`, finden Sie unter [Struktur von OLE-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Die `SCODE` wird automatisch in den `HRESULT` -Datentyp.  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)

