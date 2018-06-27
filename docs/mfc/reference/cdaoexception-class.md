---
title: CDaoException Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoException
- AFXDAO/CDaoException
- AFXDAO/CDaoException::CDaoException
- AFXDAO/CDaoException::GetErrorCount
- AFXDAO/CDaoException::GetErrorInfo
- AFXDAO/CDaoException::m_nAfxDaoError
- AFXDAO/CDaoException::m_pErrorInfo
- AFXDAO/CDaoException::m_scode
dev_langs:
- C++
helpviewer_keywords:
- CDaoException [MFC], CDaoException
- CDaoException [MFC], GetErrorCount
- CDaoException [MFC], GetErrorInfo
- CDaoException [MFC], m_nAfxDaoError
- CDaoException [MFC], m_pErrorInfo
- CDaoException [MFC], m_scode
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69d1d85f946ce596dae09779296fceab74113400
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952397"
---
# <a name="cdaoexception-class"></a>CDaoException-Klasse
Stellt eine Ausnahmebedingung dar, die von MFC-Datenbankklassen in Bezug auf Datenzugriffsobjekte (DAOs) ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoException : public CException  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException::CDaoException](#cdaoexception)|Erstellt ein `CDaoException`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException:: GetErrorCount](#geterrorcount)|Gibt die Anzahl von Fehlern in das Datenbankmodul Errors-Auflistung zurück.|  
|[CDaoException:: GetErrorInfo](#geterrorinfo)|Gibt Fehlerinformationen zu einem bestimmten Fehler-Objekt in der Auflistung von Fehlern zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|Enthält einen erweiterter Fehlercode für alle Fehler in den MFC-DAO-Klassen.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Ein Zeiger auf eine [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) -Objekt, das Informationen zu einem DAO Error-Objekt enthält.|  
|[CDaoException::m_scode](#m_scode)|Die [SCODE](#m_scode) Wert mit dem Fehler zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse enthält öffentliche Datenmember, die Sie verwenden können, um die Ursache der Ausnahme zu bestimmen. `CDaoException` Objekte werden erstellt und von Memberfunktionen von den DAO-Datenbankklassen ausgelöst.  
  
> [!NOTE]
>  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können dennoch den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC; die DAO-basierten Klassen können Daten, einschließlich der ODBC-Treiber, über eigene Datenbankmodul zugreifen. Die DAO-basierten Klassen unterstützen auch (Data Definition Language, Datendefinitionssprache)-Vorgänge, z. B. das Hinzufügen von Tabellen über die Klassen ohne DAO direkt aufrufen. Informationen zu Ausnahmen, die ausgelöst wird, durch die ODBC-Klassen finden Sie unter [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Sie erreichen Ausnahmeobjekte innerhalb des Bereichs einer [CATCH](../../mfc/reference/exception-processing.md#catch) Ausdruck. Sie können auch Auslösen `CDaoException` Objekte aus Ihrem eigenen Code mit der [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) globale Funktion.  
  
 In MFC werden alle DAO-Fehler als Ausnahmen vom Typ ausgedrückt `CDaoException`. Wenn Sie eine Ausnahme dieses Typs abfangen, können Sie `CDaoException` Memberfunktionen zum Abrufen von Informationen aus jeder DAO-Fehlerobjekte, die in das Datenbankmodul Errors-Auflistung gespeichert. Sobald ein Fehler auftritt, werden eine oder mehrere Error-Objekte in der Fehlersammlung platziert. (Normalerweise die Auflistung enthält nur ein Error-Objekt, wenn Sie eine ODBC-Datenquelle verwenden, werden Sie wahrscheinlich mehrere Fehlerobjekte werden.) Wenn ein anderer DAO-Vorgang einen Fehler generiert, wird die fehlerauflistung deaktiviert ist, und das neue Fehlerobjekt befindet sich in der Fehlersammlung. DAO-Vorgänge, die keine Fehler generieren haben keine Auswirkungen auf die fehlerauflistung.  
  
 DAO-Fehlercodes finden Sie in der Datei DAOERR. H. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriff" DAO-Hilfe.  
  
 Weitere Informationen zur Ausnahmebehandlung im allgemeinen oder über `CDaoException` Objekte finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md). Der zweite Artikel enthält Beispielcode, in dem DAO-Ausnahmebehandlung veranschaulicht.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="cdaoexception"></a>  CDaoException::CDaoException  
 Erstellt ein `CDaoException`-Objekt.  
  
```  
CDaoException();
```  
  
### <a name="remarks"></a>Hinweise  
 Normalerweise erstellt das Framework Ausnahmeobjekte aus, wenn der Code eine Ausnahme auslöst. Sie müssen nur selten ein Exception-Objekt explizit zu erstellen. Wenn Sie lösen möchten eine `CDaoException` aus Ihrem eigenen Code rufen Sie die globale Funktion [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).  
  
 Allerdings empfiehlt es sich um ein Exception-Objekt explizit zu erstellen, wenn Sie direkte Aufrufe DAO über DAO Schnittstellenzeiger vornehmen, die MFC-Klassen kapseln. In diesem Fall müssen Sie zum Abrufen von Fehlerinformationen von DAO. Angenommen Sie, ein Fehler über DAO tritt auf, wenn Sie über die DAODatabases-Schnittstelle, um einen Arbeitsbereich datenbankauflistung eine DAO-Methode aufrufen.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>Zum Abrufen der Fehlerinformationen DAO  
  
1.  Konstruieren Sie ein `CDaoException`-Objekt.  
  
2.  Rufen Sie des Ausnahmeobjekts [GetErrorCount](#geterrorcount) Member-Funktion, um zu bestimmen, wie viele Fehlerobjekte in das Datenbankmodul Errors-Auflistung sind. (Normalerweise nur ein, wenn Sie eine ODBC-Datenquelle verwenden.)  
  
3.  Rufen Sie des Ausnahmeobjekts [GetErrorInfo](#geterrorinfo) Memberfunktion versucht, eine bestimmte Error-Objekt zu einem Zeitpunkt nach Index in der Auflistung, über das Ausnahmeobjekt abzurufen. Vorstellen des Ausnahmeobjekts als Proxy für ein DAO-Fehlerobjekt.  
  
4.  Überprüfen Sie die aktuelle [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Datenstruktur, `GetErrorInfo` gibt Sie zurück die [M_pErrorInfo](#m_perrorinfo) -Datenmember. Ihre Mitglieder bieten Informationen zu den DAO-Fehler.  
  
5.  Wiederholen Sie die Schritte 3 und 4 nach Bedarf für weitere Fehlerobjekte, im Falle einer ODBC-Datenquelle.  
  
6.  Wenn Sie das Ausnahmeobjekt auf dem Heap erstellt haben, löschen Sie sie mit der **löschen** Operator, wenn Sie fertig sind.  
  
 Weitere Informationen zur Behandlung von Fehlern in den MFC-DAO-Klassen finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="geterrorcount"></a>  CDaoException:: GetErrorCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von DAO-Fehlerobjekte in das Datenbankmodul Errors-Auflistung.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der DAO-Fehlerobjekte in das Datenbankmodul Errors-Auflistung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen sind hilfreich für das Durchlaufen der fehlerauflistung um jeweils eine oder mehrere DAO Error-Objekte in der Auflistung abzurufen. Um ein Error-Objekt nach Index oder DAO-Fehlernummer abzurufen, rufen die [GetErrorInfo](#geterrorinfo) Memberfunktion.  
  
> [!NOTE]
>  Normalerweise ist nur ein Error-Objekt in der Fehlersammlung vorhanden. Wenn Sie mit einer ODBC-Datenquelle arbeiten, kann es jedoch sein mehr als ein.  
  
##  <a name="geterrorinfo"></a>  CDaoException:: GetErrorInfo  
 Gibt Fehlerinformationen zu einem bestimmten Fehler-Objekt in der Auflistung von Fehlern zurück.  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index, der die Fehlerinformationen in die Datenbank-Engine-Errors-Auflistung für die Suche nach Index.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die folgenden Arten von Informationen über die Ausnahme zu erhalten:  
  
-   Fehlercode  
  
-   Quelle  
  
-   Beschreibung  
  
-   Hilfedatei  
  
-   Hilfekontext  
  
 `GetErrorInfo` Speichert die Informationen in des Ausnahmeobjekts `m_pErrorInfo` -Datenmember. Eine kurze Beschreibung der Informationen zurückgegeben werden, finden Sie unter [M_pErrorInfo](#m_perrorinfo). Wenn Sie eine Ausnahme vom Typ abfangen `CDaoException` ausgelöst von MFC, die `m_pErrorInfo` Member bereits ausgefüllt. Falls gewünscht, DAO direkt aufrufen, müssen Sie des Ausnahmeobjekts Aufrufen `GetErrorInfo` Memberfunktion selbst füllen `m_pErrorInfo`. Eine ausführlichere Beschreibung finden Sie unter der [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Struktur.  
  
 Informationen über DAO-Ausnahmen und Beispielcode finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError  
 Enthält eine erweiterter Fehlercode MFC.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Code ist in Fällen angegeben, in denen eine bestimmte Komponente der MFC-DAO-Klassen bezieht hat.  
  
 Dabei sind folgende Werte möglich:  
  
- **NO_AFX_DAO_ERROR** zuletzt ausgeführten Vorgangs einen MFC erweiterter Fehler nicht zu. Allerdings der Vorgang konnte produziert, andere Fehler von DAO oder OLE, also überprüfen sollten [M_pErrorInfo](#m_perrorinfo) und möglicherweise [M_scode](#m_scode).  
  
- **AFX_DAO_ERROR_ENGINE_INITIALIZATION** MFC konnte nicht initialisiert werden, das Microsoft Jet-Datenbankmodul. OLE kann Fehler beim Initialisieren oder möglicherweise wurden zum Erstellen einer Instanz des DAO-Datenbankmoduls Datenbankobjekts unmöglich. Diese Probleme wird in der Regel eine fehlerhafte Installation von DAO oder OLE empfohlen.  
  
- **AFX_DAO_ERROR_DFX_BIND** eine Adresse in einem DAO-Datensatzfeldaustausch Datensatzfeldaustausch (DFX)-Funktionsaufruf verwendet, ist nicht vorhanden oder ist ungültig (die Adresse wurde nicht zum Binden von Daten verwendet). Sie haben eine ungültige Adresse können in einem DFX-Aufruf übergeben, oder die Adresse möglicherweise ungültig geworden ist zwischen DFX-Operationen.  
  
- **AFX_DAO_ERROR_OBJECT_NOT_OPEN** Sie haben versucht, öffnen Sie ein Recordset basierend auf einer Querydef oder ein Tabledef-Objekt, das nicht in einem geöffneten Status war.  
  
##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo  
 Enthält einen Zeiger auf eine `CDaoErrorInfo` -Struktur, die Informationen auf den DAO-Fehlerobjekt, die Sie zuletzt abgerufen haben bereitstellt, durch den Aufruf [GetErrorInfo](#geterrorinfo).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt enthält die folgende Informationen an:  
  
|CDaoErrorInfo-Element|Information|Bedeutung|  
|--------------------------|-----------------|-------------|  
|`m_lErrorCode`|Fehlercode|DAO-Fehlercode:|  
|`m_strSource`|Quelle|Der Name des Objekts oder der Anwendung, die ursprünglich den Fehler generiert hat|  
|`m_strDescription`|Beschreibung|Eine beschreibende Zeichenfolge, die dem Fehler zugeordnete|  
|`m_strHelpFile`|Hilfedatei|Ein Pfad zu einer Windows-Hilfe-Datei, die in der der Benutzer Informationen zu diesem Problem erhalten|  
|`m_lHelpContext`|Hilfekontext|Die Kontext-ID für ein Thema in der Hilfedatei von DAO|  
  
 Ausführliche Informationen zu den Informationen in den `CDaoErrorInfo` Objekt, finden Sie unter der [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Struktur.  
  
##  <a name="m_scode"></a>  CDaoException::m_scode  
 Enthält einen Wert vom Typ `SCODE` , die den Fehler beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein OLE-Code. Sie müssen nur selten diesen Wert verwenden, da in fast allen Fällen spezifischere MFC oder DAO-Fehlerinformationen in die andere verfügbar ist `CDaoException` Datenmember.  
  
 Informationen zu `SCODE`, finden Sie im Thema [Struktur von OLE-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) im Windows SDK. Die `SCODE` -Datentyp zugeordnet, die `HRESULT` -Datentyp.  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)
