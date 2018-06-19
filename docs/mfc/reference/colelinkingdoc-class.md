---
title: COleLinkingDoc Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe37e1a159fa0138c237b58ffbd622292dcba714
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369846"
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc-Klasse
Die Basisklasse für OLE-Containerdokumente, die das Verknüpfen mit den enthaltenen eingebetteten Elementen unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleLinkingDoc : public COleDocument  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|Erstellt ein `COleLinkingDoc`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinkingDoc::Register](#register)|Wird das Dokument mit der OLE-System-DLLs registriert.|  
|[COleLinkingDoc::Revoke](#revoke)|Hebt die Registrierung des Dokuments.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|Sucht das angegebene eingebettete Element.|  
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|Sucht das angegebene verknüpfte Element.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Steuerelementcontainer-Anwendung, die Verknüpfung mit eingebetteten Elementen unterstützt wird als "Link-Container" bezeichnet. Die [OCLIENT](../../visual-cpp-samples.md) beispielanwendung ist ein Beispiel für einen Link-Container.  
  
 Wenn ein verknüpftes Element Quelle ein eingebettetes Element in einem anderen Dokument ist, muss das enthaltende Dokument in der Reihenfolge für das eingebettete Element bearbeitet werden geladen werden. Aus diesem Grund muss ein Link Container von einem anderen containeranwendung gestartet werden, wenn der Benutzer möchte die Quelle eines verknüpften Elements bearbeiten kann. Die Anwendung muss auch verwenden, die [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) Klasse, damit es Dokumente, die beim Starten von programmgesteuert erstellen kann.  
  
 Um dem Container einen Link Container machen, leiten Sie eine Dokumentklasse von `COleLinkingDoc` anstelle von [COleDocument](../../mfc/reference/coledocument-class.md). Wie bei jedem anderen OLE-Container müssen Sie die Klasse zum Speichern von der Anwendungsverzeichnis systemeigene Daten als auch eingebettete oder verknüpfte Elemente entwerfen. Darüber hinaus müssen Sie Datenstrukturen für das Speichern Ihrer systemeigenen Daten entwerfen. Wenn Sie definieren eine `CDocItem`-abgeleitete Klasse, für Ihre Anwendung native's Daten, Sie können mithilfe dieser Schnittstelle durch definierten `COleDocument` Ihre systemeigenen Daten als auch für die OLE-Daten zu speichern.  
  
 Damit wird die Anwendung programmgesteuert von einem anderen Container gestartet werden soll, deklarieren einen `COleTemplateServer` Objekt als Mitglied der Ihre Anwendungsverzeichnis `CWinApp`-abgeleitete Klasse:  
  
 [!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]  
  
 In der `InitInstance` Memberfunktion von Ihrem `CWinApp`-abgeleitete Klasse, erstellen Sie eine Dokumentvorlage, und geben Sie Ihre `COleLinkingDoc`-abgeleitete Klasse als Dokumentklasse:  
  
 [!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]  
  
 Verbinden der `COleTemplateServer` Objekt, das die Dokumentvorlagen durch Aufrufen des Objekts `ConnectTemplate` Memberfunktion, und registrieren Sie Klasse alle Objekte mit dem OLE-System durch Aufrufen von **COleTemplateServer::RegisterAll**:  
  
 [!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]  
  
 Ein Beispiel `CWinApp`-Klassendefinition abgeleitet und `InitInstance` funktionieren, finden Sie unter OCLIENT. H und OCLIENT. CPP im MFC-Beispiel [OCLIENT](../../visual-cpp-samples.md).  
  
 Weitere Informationen zur Verwendung von `COleLinkingDoc`, finden Sie in den Artikeln [Container: Implementieren eines Containers](../../mfc/containers-implementing-a-container.md) und [Container: Erweiterte Funktionen](../../mfc/containers-advanced-features.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 `COleLinkingDoc`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxole.h  
  
##  <a name="colelinkingdoc"></a>  COleLinkingDoc::COleLinkingDoc  
 Erstellt eine `COleLinkingDoc` Objekt ohne Kommunikation mit dem OLE-System-DLLs ab.  
  
```  
COleLinkingDoc();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die `Register` Memberfunktion OLE informiert, dass das Dokument geöffnet ist.  
  
##  <a name="onfindembeddeditem"></a>  COleLinkingDoc::OnFindEmbeddedItem  
 Wird aufgerufen, durch das Framework, um zu bestimmen, ob das Dokument mit eine eingebettete OLE-Element mit dem angegebenen Namen enthält.  
  
```  
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItemName`  
 Ein Zeiger auf den Namen der eingebetteten OLE-Element angefordert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das angegebene Element; **NULL** , wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung sucht die Liste der eingebetteten Elemente für ein Element mit dem angegebenen Namen (der Namensvergleich wird die Groß-/Kleinschreibung unterschieden). Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode zum Speichern von oder benennen eingebettete OLE-Elemente haben.  
  
##  <a name="ongetlinkeditem"></a>  COleLinkingDoc::OnGetLinkedItem  
 Vom Framework aufgerufen wird, überprüfen Sie, ob das Dokument ein Verbindungsserver-Element mit dem angegebenen Namen enthält.  
  
```  
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszItemName`  
 Ein Zeiger auf den Namen der verknüpften OLE Element angefordert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das angegebene Element; **NULL** , wenn das Element nicht gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardeinstellung `COleLinkingDoc` Implementierung gibt immer **NULL**. Diese Funktion ist in der abgeleiteten Klasse überschrieben `COleServerDoc` , die Liste der OLE-Server-Elemente für ein verknüpftes Element mit dem angegebenen Namen gesucht werden soll (der Namensvergleich wird die Groß-/Kleinschreibung unterschieden). Überschreiben Sie diese Funktion, wenn Sie eine eigene Methode zum Speichern von oder Abrufen von Elementen der Verbindungsserver implementiert haben.  
  
##  <a name="register"></a>  COleLinkingDoc::Register  
 Informiert der OLE-System-DLLs, dass das Dokument geöffnet ist.  
  
```  
BOOL Register(
    COleObjectFactory* pFactory,  
    LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Parameter  
 *pFactory*  
 Zeiger auf ein OLE-Factory-Objekt (kann **NULL**).  
  
 `lpszPathName`  
 Ein Zeiger auf den vollqualifizierten Pfad des Containerdokuments.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dokument erfolgreich registriert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird beim Erstellen oder öffnen eine benannte Datei aus, um das Dokument mit der OLE-System-DLLs zu registrieren. Es ist nicht erforderlich, diese Funktion aufzurufen, wenn das Dokument ein eingebettetes Element darstellt.  
  
 Bei Verwendung von `COleTemplateServer` in Ihrer Anwendung `Register` wird aufgerufen, für Sie von `COleLinkingDoc`der Implementierung von `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
##  <a name="revoke"></a>  COleLinkingDoc::Revoke  
 Informiert der OLE-System-DLLs, dass das Dokument nicht mehr geöffnet ist.  
  
```  
void Revoke();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um das Dokument die Registrierung mit OLE-System-DLLs zu widerrufen.  
  
 Sie sollten diese Funktion beim Schließen einer benannten Datei aufrufen, aber Sie in der Regel müssen nicht direkt aufgerufen. `Revoke` wird aufgerufen, für Sie von `COleLinkingDoc`der Implementierung von `OnCloseDocument`, `OnNewDocument`, `OnOpenDocument`, und `OnSaveDocument`.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel OCLIENT](../../visual-cpp-samples.md)   
 [COleDocument-Klasse](../../mfc/reference/coledocument-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDocTemplate-Klasse](../../mfc/reference/cdoctemplate-class.md)
