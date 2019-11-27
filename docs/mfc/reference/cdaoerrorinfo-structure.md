---
title: CDaoErrorInfo-Struktur
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: 8d731c8e8bea1adc850ab3c00c7688b9f8c9b819
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304227"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo-Struktur

Die `CDaoErrorInfo`-Struktur enthält Informationen zu einem Fehler Objekt, das für Data Access Objects (DAO) definiert ist. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird.

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

Die MFC-Klasse enthält keine DAO-Fehler Objekte in einer Klasse. Stattdessen stellt die [CDaoException](../../mfc/reference/cdaoexception-class.md) -Klasse eine Schnittstelle für den Zugriff auf die Fehler Auflistung im DAO-`DBEngine` Objekt bereit, das Objekt, das auch alle Arbeitsbereiche enthält. Wenn ein MFC-DAO-Vorgang ein `CDaoException` Objekt auslöst, das Sie abfangen, füllt MFC eine `CDaoErrorInfo` Struktur und speichert Sie im [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Member des Ausnahme Objekts. (Wenn Sie DAO direkt aufrufen möchten, müssen Sie die [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) -Member-Funktion des Exception-Objekts selbst aufrufen, um `m_pErrorInfo`auszufüllen.)

Weitere Informationen zur Behandlung von DAO-Fehlern finden Sie im Artikel [Ausnahmen: Daten Bank Ausnahmen](../../mfc/exceptions-database-exceptions.md). Weitere Informationen finden Sie im Thema "Fehler Objekt" in der DAO-Hilfe.

Informationen, die von der [CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) -Member-Funktion abgerufen werden, werden in einer `CDaoErrorInfo` Struktur gespeichert. Untersuchen Sie das [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Datenmember von einem `CDaoException` Objekt, das Sie in einem Ausnahmehandler abgefangen haben, oder rufen Sie `GetErrorInfo` von einem `CDaoException` Objekt auf, das Sie explizit erstellen, um Fehler zu überprüfen, die möglicherweise während eines direkten Aufrufes der DAO-Schnittstellen aufgetreten sind. `CDaoErrorInfo` definiert auch eine `Dump` Member-Funktion in Debugbuilds. Sie können `Dump` verwenden, um den Inhalt eines `CDaoErrorInfo` Objekts zu speichern.

## <a name="requirements"></a>Voraussetzungen

**Header:** afxdao.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
