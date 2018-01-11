---
title: CDaoErrorInfo-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoErrorInfo
dev_langs: C++
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da47b4b68a9fd73b3962254121006eff47282336
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo-Struktur
Die `CDaoErrorInfo` Struktur enthält Informationen zu einem Fehlerobjekt, das für Datenzugriffsobjekte (DAO) definiert.  
  
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
 *m_lErrorCode*  
 Eine numerische DAO-Fehlercode. Finden Sie im Thema "Abfangbarer Datenzugriff" DAO-Hilfe aus.  
  
 *m_strSource*  
 Der Name des Objekts oder der Anwendung, die ursprünglich den Fehler generiert hat. Die Source-Eigenschaft gibt einen Zeichenfolgenausdruck für das Objekt, das ursprünglich den Fehler generiert hat. der Ausdruck ist in der Regel den Namen des Objekts-Klasse. Details finden Sie im Thema "Quelleigenschaft" DAO-Hilfe.  
  
 *m_strDescription*  
 Eine beschreibende Zeichenfolge, die mit einem Fehler verknüpft sind. Details finden Sie im Thema "Description-Eigenschaft" DAO-Hilfe.  
  
 *m_strHelpFile*  
 Einen vollqualifizierten Pfad zu einer Microsoft Windows-Hilfe-Datei. Weitere Informationen finden Sie im Thema "HelpContext HelpFile-Eigenschaften" in der Hilfe von DAO ein.  
  
 *m_lHelpContext*  
 Eine Kontext-ID für ein Thema in einer Microsoft Windows-Hilfedatei. Weitere Informationen finden Sie im Thema "HelpContext HelpFile-Eigenschaften" in der Hilfe von DAO ein.  
  
## <a name="remarks"></a>Hinweise  
 MFC ist DAO-Fehlerobjekte in einer Klasse nicht gekapselt werden. Stattdessen die [CDaoException](../../mfc/reference/cdaoexception-class.md) -Klasse stellt eine Schnittstelle für den Zugriff auf die Errors-Auflistung enthalten sind, die über DAO **Datenbankmodul** -Objekt, das Objekt, das auch alle Arbeitsbereiche enthält. Wenn ein MFC-DAO-Vorgang löst eine `CDaoException` Objekt, das Sie abfangen, MFC füllt eine `CDaoErrorInfo` Struktur und speichert ihn in des Ausnahmeobjekts [M_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Member. (Falls gewünscht, DAO direkt aufrufen, müssen Sie des Ausnahmeobjekts Aufrufen [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) Memberfunktion selbst füllen `m_pErrorInfo`.)  
  
 Weitere Informationen zur Behandlung von DAO-Fehlern finden Sie im Artikel [Ausnahmen: Datenbankausnahmen](../../mfc/exceptions-database-exceptions.md). Verwandte Informationen finden Sie im Thema "Error-Objekt" DAO-Hilfe.  
  
 Informationen, die abgerufen, indem die [CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) Memberfunktion befindet sich in einer `CDaoErrorInfo` Struktur. Untersuchen der [M_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) Datenmember aus einer `CDaoException` -Objekt, das Sie in einem Ausnahmehandler oder einen Aufruf abfangen `GetErrorInfo` aus einer `CDaoException` -Objekt, das Sie explizit erstellen, um Fehler zu überprüfen, die möglicherweise Bei der ein direkter Aufruf die DAO-Schnittstellen. `CDaoErrorInfo`definiert auch einen `Dump` Memberfunktion in Debug-builds. Sie können `Dump` auf den Inhalt des Basisklassenobjekts auszugeben ein `CDaoErrorInfo` Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
