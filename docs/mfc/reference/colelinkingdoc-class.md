---
title: Klasse COleLinkingDoc | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleLinkingDoc class
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
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
ms.openlocfilehash: acdfde1413d5ff93efc63dbbf211881f71cf624e
ms.lasthandoff: 02/24/2017

---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc-Klasse
Die Basisklasse für OLE-Containerdokumente, die das Verknüpfen mit den enthaltenen eingebetteten Elementen unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Erstellt ein `COleLinkingDoc`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|Das Dokument registriert die OLE-System-DLLs.|  
|[COleLinkingDoc::Revoke](#revoke)|Hebt die Registrierung des Dokuments.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Sucht die angegebene eingebettete.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Sucht das angegebene verknüpfte Element.|  
  
## <a name="remarks"></a>Hinweise  
 Eine containeranwendung, die Verknüpfen mit eingebetteten Elementen unterstützt wird einen "Link-Container" bezeichnet. Die [OCLIENT](../../visual-cpp-samples.md) Anwendung ist ein Beispiel für einen Link-Container.  
  
 Wenn ein verknüpftes Element Quelle ein eingebettetes Element in einem anderen Dokument ist, muss das enthaltende Dokument in der Reihenfolge für das eingebettete Element bearbeitet werden geladen werden. Aus diesem Grund muss ein Link-Container können durch eine andere containeranwendung gestartet wird, wenn der Benutzer die Quelle eines verknüpften Elements bearbeiten möchte. Ihre Anwendung muss auch verwendet die [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) -Klasse so, dass es Dokumente, die beim Start von programmgesteuert erstellen kann.  
  
 Um dem Container für eine Link-Container zu machen, leiten Sie die Dokumentklasse von `COleLinkingDoc` anstelle von [COleDocument](../../mfc/reference/coledocument-class.md). Wie bei jedem anderen OLE-Container, müssen Sie die Klasse zum Speichern der Anwendungsverzeichnis systemeigene Daten als auch eingebettete oder verknüpfte Elemente entwerfen. Darüber hinaus müssen Sie Datenstrukturen für das Speichern von systemeigenen Daten entwerfen. Wenn Sie definieren eine `CDocItem`-abgeleitete Klasse, die Anwendung dann den systemeigenen Daten, können Sie die Schnittstelle definiert `COleDocument` Ihre systemeigenen Daten als auch für die OLE-Daten zu speichern.  
  
 Um die Anwendung programmgesteuert durch einen anderen Container gestartet werden können, deklarieren ein `COleTemplateServer` -Objekt als Member von Ihrer Anwendungsverzeichnis `CWinApp`-abgeleiteten Klasse:  
  
 [!code-cpp[NVC_MFCOleContainer&23;](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 In der `InitInstance` Memberfunktion Ihre `CWinApp`-abgeleiteten Klasse eine Dokumentvorlage erstellen, und geben Sie Ihre `COleLinkingDoc`-abgeleitete Klasse als Dokumentklasse:  
  
 [!code-cpp[NVC_MFCOleContainer&#24;](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Verbinden Ihrer `COleTemplateServer` Objekt, das Ihren Dokumentvorlagen durch Aufrufen des Objekts `ConnectTemplate` -Memberfunktion, und registrieren Sie alle Klasse Objekte mit der OLE-System durch Aufrufen von **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer&#25;](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Ein Beispiel für die `CWinApp`-Definition der Klasse abgeleitet und `InitInstance` finden Sie im OCLIENT. H und OCLIENT. CPP im MFC-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
 Weitere Informationen zur Verwendung von `COleLinkingDoc`, finden Sie in den Artikeln [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Container: Erweiterte Features](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="colelinkingdoc"></a>COleLinkingDoc::COleLinkingDoc  
 Erstellt ein `COleLinkingDoc` Objekt ohne Kommunikation mit dem OLE-System-DLLs ab.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie aufrufen, die `Register` Memberfunktion OLE informiert, dass das Dokument geöffnet ist.  
  
##  <a name="onfindembeddeditem"></a>COleLinkingDoc::OnFindEmbeddedItem  
 Aufgerufen, um zu bestimmen, ob das Dokument mit eine eingebettete OLE-Element mit dem angegebenen Namen enthält.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItemName`  
 Zeiger auf den Namen der eingebetteten OLE-Element angefordert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das angegebene Element; **NULL** Wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sucht die Liste der eingebetteten Elemente für ein Element mit dem angegebenen Namen (die beim Vergleich wird die Groß-/Kleinschreibung beachten). Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode zum Speichern, oder benennen eingebettete OLE-Elemente haben.  
  
##  <a name="ongetlinkeditem"></a>COleLinkingDoc::OnGetLinkedItem  
 Vom Framework aufgerufen wird, überprüfen Sie, ob das Dokument ein Verbindungsserver-Element mit dem angegebenen Namen enthält.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItemName`  
 Zeiger auf den Namen der verknüpften OLE-Element angefordert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das angegebene Element; **NULL** Wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung `COleLinkingDoc` Implementierung gibt immer **NULL**. Diese Funktion ist in der abgeleiteten Klasse überschrieben `COleServerDoc` die Liste der OLE-Server-Elemente für ein verknüpftes Element mit dem angegebenen Namen gesucht (die beim Vergleich wird die Groß-/Kleinschreibung beachten). Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode speichern oder Abrufen von Elementen Verbindungsserver implementiert haben.  
  
##  <a name="register"></a>COleLinkingDoc::Register  
 Informiert, dass das Dokument geöffnet ist der OLE-System-DLLs.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 *pFactory*  
 Zeiger auf ein OLE-Objekt-Factory (kann **NULL**).  
  
 `lpszPathName`  
 Ein Zeiger auf den vollqualifizierten Pfad des Containerdokuments.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich registriert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion beim Erstellen oder öffnen eine benannte Datei aus, um das Dokument mit der OLE-System-DLLs registrieren. Es ist nicht erforderlich, diese Funktion aufzurufen, wenn das Dokument ein eingebettetes Element darstellt.  
  
 Bei Verwendung von `COleTemplateServer` in Ihrer Anwendung `Register` heißt vom `COleLinkingDoc`der Implementierung von `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
##  <a name="revoke"></a>COleLinkingDoc::Revoke  
 Informiert, dass das Dokument nicht mehr öffnen Sie der OLE-System-DLLs.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um das Dokument die Registrierung mit OLE-System-DLLs zu widerrufen.  
  
 Sie sollten diese Funktion aufrufen, beim Schließen einer benannten Datei, Sie in der Regel müssen jedoch nicht direkt aufgerufen. `Revoke`wird aufgerufen, vom `COleLinkingDoc`der Implementierung von `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)

