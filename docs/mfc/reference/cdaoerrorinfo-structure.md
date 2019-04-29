---
title: CDaoErrorInfo-Struktur
ms.date: 11/04/2016
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: dd9610fce88c18ac42de81ed712492766ee705de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399846"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo-Struktur

Die `CDaoErrorInfo` Struktur enthält Informationen über ein Fehlerobjekt, das für Datenzugriffsobjekte (DAO) definiert.

## <a name="syntax"></a>Syntax

```
struct CDaoErrorInfo
{
    long m_lErrorCode;
    CString m_strSource;
    CString m_strDescription;
    CString m_strHelpFile;
    long m_lHelpContext;
};
```

#### <a name="parameters"></a>Parameter

*m_lErrorCode*<br/>
Ein numerischer DAO-Fehlercode. Finden Sie im Thema "Abfangbarer Datenzugriffsfehlern" in-DAO-Hilfe aus.

*m_strSource*<br/>
Der Name des Objekts oder der Anwendung, die den Fehler ursprünglich generiert hat. Die Source-Eigenschaft gibt an, einen Zeichenfolgenausdruck, der das Objekt, das den Fehler ursprünglich generiert hat. der Ausdruck ist in der Regel den Namen des Objekts-Klasse. Informationen finden Sie im Thema "Source-Eigenschaft" in-DAO-Hilfe.

*m_strDescription*<br/>
Eine beschreibende Zeichenfolge, die mit einem Fehler verknüpft ist. Weitere Informationen finden Sie unter dem Thema "Description-Eigenschaft" in-DAO-Hilfe.

*m_strHelpFile*<br/>
Einen vollqualifizierten Pfad zu einer Microsoft Windows-Hilfedatei. Informationen finden Sie im Thema "HelpContext, HelpFile-Eigenschaft" in-DAO-Hilfe.

*m_lHelpContext*<br/>
Eine Kontext-ID für ein Thema in einer Microsoft Windows-Hilfedatei. Informationen finden Sie im Thema "HelpContext, HelpFile-Eigenschaft" in-DAO-Hilfe.

## <a name="remarks"></a>Hinweise

MFC ist-DAO-Error-Objekte in einer Klasse nicht gekapselt werden. Stattdessen die [CDaoException](../../mfc/reference/cdaoexception-class.md) -Klasse stellt eine Schnittstelle für den Zugriff auf der Fehlersammlung enthalten, die über DAO `DBEngine` -Objekt, das Objekt, das auch alle Arbeitsbereiche enthält. Wenn ein MFC-DAO-Vorgang löst einen `CDaoException` Objekt, dass Sie abfangen, füllt der MFC eine `CDaoErrorInfo` strukturieren und speichert sie in des Ausnahmeobjekts [M_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Member. (Wenn Sie die DAO direkt aufrufen möchten, müssen Sie des Ausnahmeobjekts Aufrufen [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) Memberfunktion selbst zum Ausfüllen `m_pErrorInfo`.)

Weitere Informationen zur Behandlung von DAO-Fehlern finden Sie im Artikel [Ausnahmen: Datenbank-Ausnahmen](../../mfc/exceptions-database-exceptions.md). Verwandte Informationen finden Sie im Thema "Error-Objekt" in-DAO-Hilfe.

Informationen, die abgerufen, indem die [CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) Member-Funktion befindet sich in einem `CDaoErrorInfo` Struktur. Überprüfen der [M_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Datenmember aus einer `CDaoException` -Objekt, das Sie in einem Ausnahmehandler oder Aufruf abfangen `GetErrorInfo` aus einer `CDaoException` -Objekt, das Sie explizit erstellen, um Fehler zu überprüfen, die möglicherweise Bei einem direkten Aufruf die DAO-Schnittstellen ist aufgetreten. `CDaoErrorInfo` definiert auch eine `Dump` -Memberfunktion im Debug-builds. Können Sie `Dump` zum Sichern den Inhalt einer `CDaoErrorInfo` Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
