---
title: CDaoException-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: fbcabd0659e98d25cbe28ce233b89dccc3585d61
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336185"
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
|[CDaoException:: GetErrorCount](#geterrorcount)|Gibt die Anzahl von Fehlern in der Datenbank-Engine Errors-Collection zurück.|  
|[CDaoException:: GetErrorInfo](#geterrorinfo)|Gibt Informationen zu einem bestimmten Fehler-Objekt in der Auflistung von Fehlern zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoException::m_nAfxDaoError](#m_nafxdaoerror)|Enthält einen erweiterter Fehlercode für alle Fehler in den MFC-DAO-Klassen.|  
|[CDaoException::m_pErrorInfo](#m_perrorinfo)|Ein Zeiger auf eine [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) -Objekt, das Informationen zu einem DAO-Error-Objekt enthält.|  
|[CDaoException::m_scode](#m_scode)|Die [SCODE](#m_scode) Wert mit dem Fehler zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse enthält öffentliche Datenmember, die Sie verwenden können, um die Ursache der Ausnahme zu bestimmen. `CDaoException` Objekte werden erstellt und von Memberfunktionen von den DAO-Datenbankklassen ausgelöst.  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können weiterhin den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC; die DAO-basierten Klassen können Daten, einschließlich über ODBC-Treiber, über eigene Datenbank-Engine zugreifen. Die DAO-basierten Klassen unterstützen auch Vorgänge wie das Hinzufügen von Tabellen über die Klassen, ohne direkt aufrufen von DAO (Data Definition Language, Datendefinitionssprache). Weitere Informationen zu Ausnahmen, die von der ODBC-Klassen ausgelöst werden, finden Sie unter [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Sie erreichen die Exception-Objekte innerhalb des Bereichs einer [CATCH](../../mfc/reference/exception-processing.md#catch) Ausdruck. Sie können auch auslösen, `CDaoException` Objekte über Ihren eigenen Code mit der [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception) globale Funktion.  
  
 In MFC werden alle DAO-Fehler als Ausnahmen vom Typ ausgedrückt `CDaoException`. Wenn Sie eine Ausnahme dieses Typs abzufangen, können Sie `CDaoException` Memberfunktionen zum Abrufen von Informationen aus den klassentypobjekte Fehler DAO in der Datenbank-Engine-Fehler-Auflistung gespeichert. Sobald ein Fehler auftritt, werden ein oder mehrere Fehlerobjekte in der fehlerauflistung platziert. (Normalerweise die Auflistung enthält nur ein Fehlerobjekt, wenn Sie eine ODBC-Datenquelle verwenden, sind Sie wahrscheinlich mehrere Fehlerobjekte abzurufen.) Wenn ein anderer DAO-Vorgang einen Fehler generiert, wird die fehlerauflistung deaktiviert ist, und das neue Fehlerobjekt befindet sich in der fehlerauflistung. DAO-Vorgänge, die keinen Fehler generieren wirken sich nicht auf die Fehlersammlung aus.  
  
 DAO-Fehlercodes finden Sie in der Datei DAOERR. H. Verwandte Informationen finden Sie im Thema "Abfangbarer Datenzugriffsfehlern" in-DAO-Hilfe.  
  
 Weitere Informationen zur Behandlung von Ausnahmen in allgemeinen oder etwa `CDaoException` Objekten finden Sie in den Artikeln [Ausnahmebehandlung (MFC)](../../mfc/exception-handling-in-mfc.md) und [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md). Der zweite Artikel enthält Beispielcode, der die Ausnahmebehandlung in-DAO-veranschaulicht.  
  
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
 Normalerweise erstellt das Framework Exception-Objekte aus, wenn der Code eine Ausnahme auslöst. Sie müssen nur selten explizit ein Exception-Objekt zu erstellen. Wenn Sie auslösen möchten, eine `CDaoException` über Ihren eigenen Code verwenden, rufen Sie die globale Funktion [AfxThrowDaoException](../../mfc/reference/exception-processing.md#afxthrowdaoexception).  
  
 Allerdings empfiehlt es sich um ein Exception-Objekt explizit zu erstellen, wenn Sie direkte Aufrufe DAO über die DAO-Schnittstellenzeiger vornehmen, die MFC-Klassen kapseln. In diesem Fall müssen Sie möglicherweise zum Abrufen von Fehlerinformationen aus dem DAO. Nehmen wir an, dass ein Fehler in-DAO-tritt auf, wenn Sie über die DAODatabases-Schnittstelle, um einen Arbeitsbereich in der datenbankauflistung eine DAO-Methode aufrufen.  
  
##### <a name="to-retrieve-the-dao-error-information"></a>Zum Abrufen der DAO-Fehlerinformationen  
  
1.  Konstruieren Sie ein `CDaoException`-Objekt.  
  
2.  Rufen Sie des Ausnahmeobjekts [GetErrorCount](#geterrorcount) Memberfunktion, um zu bestimmen, wie viele Fehlerobjekte in der Datenbank-Engine-fehlerauflistung sind. (Normalerweise ein, wenn Sie eine ODBC-Datenquelle verwenden.)  
  
3.  Rufen Sie des Ausnahmeobjekts [GetErrorInfo](#geterrorinfo) Memberfunktion versucht, eine bestimmte Error-Objekt zu einem Zeitpunkt nach Index in der Auflistung, über das Ausnahmeobjekt abzurufen. Stellen Sie sich das Ausnahmeobjekt als Proxy für ein DAO-Fehlerobjekt.  
  
4.  Überprüfen Sie die aktuelle [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Datenstruktur, `GetErrorInfo` gibt Sie zurück die [M_pErrorInfo](#m_perrorinfo) -Datenmember. Ihre Mitglieder bieten Informationen zu den DAO-Fehler.  
  
5.  Wiederholen Sie Schritte 3 und 4 nach Bedarf für weitere Fehlerobjekte, im Fall von einer ODBC-Datenquelle.  
  
6.  Wenn Sie die Exception-Objekt, auf dem Heap erstellt haben, löschen Sie sie mit der **löschen** Operator, wenn Sie fertig sind.  
  
 Weitere Informationen zur Behandlung von Fehlern in den MFC-DAO-Klassen finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="geterrorcount"></a>  CDaoException:: GetErrorCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der DAO-Fehlerobjekte, in der Datenbank-Engine-Fehler-Auflistung.  
  
```  
short GetErrorCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der DAO-Fehlerobjekte, in der Datenbank-Engine-Fehler-Auflistung.  
  
### <a name="remarks"></a>Hinweise  
 Diese Informationen sind hilfreich für das Durchlaufen der Fehlersammlung jeweils eine oder mehrere DAO-Error-Objekte in der Auflistung abgerufen. Um ein Error-Objekt nach Index oder DAO-Fehlernummer abzurufen, rufen die [GetErrorInfo](#geterrorinfo) Member-Funktion.  
  
> [!NOTE]
>  Normalerweise ist gibt es nur ein Fehlerobjekt in der Auflistung der Fehler. Wenn Sie mit einer ODBC-Datenquelle arbeiten, jedoch gibt es möglicherweise mehrere.  
  
##  <a name="geterrorinfo"></a>  CDaoException:: GetErrorInfo  
 Gibt Informationen zu einem bestimmten Fehler-Objekt in der Auflistung von Fehlern zurück.  
  
```  
void GetErrorInfo(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der Index der Fehlerinformationen in die Datenbank-Engine-Fehler-Auflistung, für die Suche nach Index.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um die folgenden Arten von Informationen über die Ausnahme zu erhalten:  
  
-   Fehlercode  
  
-   Quelle  
  
-   Beschreibung  
  
-   Hilfedatei  
  
-   Hilfekontext  
  
 `GetErrorInfo` Speichert die Informationen in des Ausnahmeobjekts `m_pErrorInfo` -Datenmember. Eine kurze Beschreibung der Informationen zurückgegeben werden soll, finden Sie unter [M_pErrorInfo](#m_perrorinfo). Wenn Sie eine Ausnahme vom Typ `CDaoException` ausgelöst von MFC, die `m_pErrorInfo` Member bereits automatisch ausgefüllt. Wenn Sie die DAO direkt aufrufen möchten, müssen Sie des Ausnahmeobjekts Aufrufen `GetErrorInfo` Memberfunktion selbst zum Ausfüllen `m_pErrorInfo`. Eine ausführlichere Beschreibung finden Sie unter den [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Struktur.  
  
 Informationen über DAO-Ausnahmen und Beispielcode finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md).  
  
##  <a name="m_nafxdaoerror"></a>  CDaoException::m_nAfxDaoError  
 Enthält eine erweiterte Fehlercode MFC.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Code wird bereitgestellt, in Fällen, in denen eine bestimmte Komponente der MFC-DAO-Klassen bezieht hat.  
  
 Dabei sind folgende Werte möglich:  
  
- NO_AFX_DAO_ERROR, die zuletzt ausgeführten Vorgangs nicht in einer MFC ergeben hat erweiterter Fehler. Aber der Vorgang konnte produziert, andere Fehler von DAO oder OLE, also Sie checken [M_pErrorInfo](#m_perrorinfo) und möglicherweise [M_scode](#m_scode).  
  
- AFX_DAO_ERROR_ENGINE_INITIALIZATION MFC konnte die Microsoft Jet-Datenbank-Engine nicht initialisiert werden. OLE kann Fehler beim Initialisieren, oder es wurden möglicherweise nicht möglich, eine Instanz der DAO-Datenbank-Engine-Objekt zu erstellen. Diese Probleme empfiehlt es sich in der Regel um eine fehlerhafte Installation von DAO- oder OLE.  
  
- AFX_DAO_ERROR_DFX_BIND eine Adresse in einem Funktionsaufruf für DAO-Datensatzfeldaustausch Datensatzfeldaustausch (DFX) verwendet, ist nicht vorhanden oder ist ungültig (die Adresse wurde nicht zum Binden von Daten verwendet). Sie haben eine ungültige Adresse können in einem DFX-Aufruf übergeben, oder die Adresse möglicherweise ungültig geworden zwischen DFX-Operationen.  
  
- AFX_DAO_ERROR_OBJECT_NOT_OPEN Sie versucht, ein Recordset basierend auf einer Querydef oder ein Tabledef-Objekt, das nicht im geöffneten Zustand wurde geöffnet.  
  
##  <a name="m_perrorinfo"></a>  CDaoException::m_pErrorInfo  
 Enthält einen Zeiger auf eine `CDaoErrorInfo` -Struktur, die Informationen für den DAO-Error-Objekt, die Sie zuletzt abgerufen haben bereitstellt, durch den Aufruf [GetErrorInfo](#geterrorinfo).  
  
### <a name="remarks"></a>Hinweise  
 Dieses Objekt enthält die folgende Informationen an:  
  
|CDaoErrorInfo-Element|Information|Bedeutung|  
|--------------------------|-----------------|-------------|  
|`m_lErrorCode`|Fehlercode|DAO-Fehlercode:|  
|`m_strSource`|Quelle|Der Name des Objekts oder der Anwendung, die den Fehler ursprünglich generiert hat|  
|`m_strDescription`|Beschreibung|Eine beschreibende Zeichenfolge, die mit dem Fehler verknüpfte|  
|`m_strHelpFile`|Hilfedatei|Ein Pfad zu einer Windows-Hilfedatei in der der Benutzer Informationen zu diesem Problem erhalten|  
|`m_lHelpContext`|Hilfekontext|Die Kontext-ID für ein Thema in der Hilfedatei von DAO|  
  
 Ausführliche Informationen zu den Informationen in den `CDaoErrorInfo` Objekt, finden Sie unter den [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) Struktur.  
  
##  <a name="m_scode"></a>  CDaoException::m_scode  
 Enthält einen Wert vom Typ `SCODE` , die den Fehler beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist ein OLE-Code. Sie benötigen nur selten, diesen Wert verwenden, da in fast allen Fällen spezifischere MFC oder DAO-Fehlerinformationen zur Verfügung, in der anderen ist `CDaoException` Datenmember.  
  
 Informationen zu SCODE, finden Sie im Thema [Struktur von OLE-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) im Windows SDK. Der Datentyp SCODE ordnet den HRESULT-Datentyp.  
  
## <a name="see-also"></a>Siehe auch  
 [CException-Klasse](../../mfc/reference/cexception-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CException-Klasse](../../mfc/reference/cexception-class.md)
