---
title: CDaoErrorInfo-Struktur
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: a7b273bd2aa6b428bf795c1842455b8bfe187cc8
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096138"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo-Struktur

Die `CDaoErrorInfo` Struktur enthält Informationen über ein für Data Access Objects (DAO) definiertes Fehler Objekt.
DAO 3,6 ist die endgültige Version und wird als veraltet eingestuft.


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
Ein numerischer DAO-Fehlercode. Weitere Informationen finden Sie in der DAO-Hilfe im Thema "Abfang Bare Datenzugriffs Fehler".

*m_strSource*<br/>
Der Name des Objekts oder der Anwendung, das ursprünglich den Fehler generiert hat. Die Source-Eigenschaft gibt einen Zeichen folgen Ausdruck an, der das Objekt darstellt, das ursprünglich den Fehler generiert hat. der Ausdruck ist normalerweise der Klassenname des Objekts. Weitere Informationen finden Sie im Thema "Quell Eigenschaft" in der DAO-Hilfe.

*m_strDescription*<br/>
Eine beschreibende Zeichenfolge, die einem Fehler zugeordnet ist. Weitere Informationen finden Sie im Thema "Description Property" in der DAO-Hilfe.

*m_strHelpFile*<br/>
Ein voll qualifizierter Pfad zu einer Microsoft Windows-Hilfedatei. Weitere Informationen finden Sie im Thema "HelpContext, HelpFile Properties" in der DAO-Hilfe.

*m_lHelpContext*<br/>
Eine Kontext-ID für ein Thema in einer Microsoft Windows-Hilfedatei. Weitere Informationen finden Sie im Thema "HelpContext, HelpFile Properties" in der DAO-Hilfe.

## <a name="remarks"></a>Hinweise

Die MFC-Klasse enthält keine DAO-Fehler Objekte in einer Klasse. Stattdessen stellt die [CDaoException](../../mfc/reference/cdaoexception-class.md) -Klasse eine Schnittstelle für den Zugriff auf die im DAO `DBEngine` -Objekt enthaltene Fehler Auflistung, das-Objekt, das auch alle Arbeitsbereiche enthält, bereit. Wenn ein MFC-DAO-Vorgang `CDaoException` ein-Objekt auslöst, das Sie abfangen `CDaoErrorInfo` , füllt MFC eine Struktur und speichert Sie im [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) -Member des Ausnahme Objekts. (Wenn Sie DAO direkt aufrufen möchten, müssen Sie die [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) -Member-Funktion des Ausnahme Objekts selbst aufrufen, `m_pErrorInfo`um auszufüllen.)

Weitere Informationen zur Behandlung von DAO-Fehlern finden Sie im [Artikel Ausnahmen: Daten Bank](../../mfc/exceptions-database-exceptions.md)Ausnahmen. Weitere Informationen finden Sie im Thema "Fehler Objekt" in der DAO-Hilfe.

Informationen, die von der [CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) -Member-Funktion abgerufen `CDaoErrorInfo` werden, werden in einer Struktur gespeichert. Untersuchen Sie den [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) -Datenmember aus einem `CDaoException` -Objekt, das Sie in einem Ausnahmehandler erfassen, oder rufen `GetErrorInfo` Sie von einem `CDaoException` -Objekt auf, das Sie explizit erstellen, um Fehler zu überprüfen, die möglicherweise während eines direkten Aufrufes an die DAO-Schnittstellen. `CDaoErrorInfo`definiert auch eine `Dump` Member-Funktion in Debugbuilds. Sie können verwenden `Dump` , um den Inhalt `CDaoErrorInfo` eines-Objekts zu speichern.

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
