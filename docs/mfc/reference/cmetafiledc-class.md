---
title: CMetaFileDC-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMetaFileDC
- AFXEXT/CMetaFileDC
- AFXEXT/CMetaFileDC::CMetaFileDC
- AFXEXT/CMetaFileDC::Close
- AFXEXT/CMetaFileDC::CloseEnhanced
- AFXEXT/CMetaFileDC::Create
- AFXEXT/CMetaFileDC::CreateEnhanced
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC [MFC], CMetaFileDC
- CMetaFileDC [MFC], Close
- CMetaFileDC [MFC], CloseEnhanced
- CMetaFileDC [MFC], Create
- CMetaFileDC [MFC], CreateEnhanced
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaec2b7951b0655a8a47106374c7527dad27bd20
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039536"
---
# <a name="cmetafiledc-class"></a>CMetaFileDC-Klasse
Implementiert eine Windows-Metadatei, die eine Sequenz von Graphics Device Interface (GDI)-Befehlen enthält, dass Sie wiedergeben können, um ein gewünschtes Bild oder einen Text zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](#cmetafiledc)|Erstellt ein `CMetaFileDC`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMetaFileDC::Close](#close)|Schließt den Gerätekontext und erstellt ein Metadateihandle.|  
|[CMetaFileDC::CloseEnhanced](#closeenhanced)|Schließt eine EMF-Gerätekontext und erstellt eine EMF-Handle.|  
|[CMetaFileDC::Create](#create)|Erstellt die Windows-Metadatei-Gerätekontext und fügt es der `CMetaFileDC` Objekt.|  
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Erstellt einen Gerätekontext Metadatei für eine EMF-Datei an.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Windows-Metadatei zu implementieren, erstellen Sie zunächst eine `CMetaFileDC` Objekt. Aufrufen der `CMetaFileDC` Konstruktor, rufen Sie anschließend die [erstellen](#create) Memberfunktion, die erstellt einen Gerätekontext für Windows-Metadatei, und fügt es der `CMetaFileDC` Objekt.  
  
 Als Nächstes senden die `CMetaFileDC` Objekt die Abfolge der `CDC` GDI-Befehle, die Sie aufbewahren dafür wiedergeben. Nur für diejenigen GDI-Befehle, die Ausgabe, wie z. B. erstellen `MoveTo` und `LineTo`, kann verwendet werden.  
  
 Nachdem Sie die gewünschten Befehle an der Metadatei gesendet haben, rufen Sie die `Close` Memberfunktion ist, schließt der Metadatei Gerätekontexte aus, und gibt ein Metadateihandle zurück. Klicken Sie dann löschen Sie die `CMetaFileDC` Objekt.  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) können Sie die Metadateihandle die Metadatei wiederholt abgespielt. Die Metadatei kann auch bearbeitet werden, die Windows-Funktionen wie z. B. [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), die eine Metadatei auf den Datenträger kopiert.  
  
 Bei die Metadatei nicht mehr benötigt wird, löschen Sie es aus dem Arbeitsspeicher mit der [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows-Funktion.  
  
 Sie können auch implementieren die `CMetaFileDC` Objekt, sodass er behandeln kann beide Aufrufe ausgeben und Attribut GDI-Aufrufe wie z. B. `GetTextExtent`. Eine solche Metadatei ist flexibler und kann mehrere problemlos allgemeine GDI-Code, der aus der Ausgabe und Attribut Aufrufe häufig besteht aus wiederverwendet. Die `CMetaFileDC` Klasse erbt, zwei Gerätekontexte `m_hDC` und `m_hAttribDC`, aus `CDC`. Die `m_hDC` Gerätekontext verarbeitet alle [CDC](../../mfc/reference/cdc-class.md) GDI Ausgabe Aufrufe und die `m_hAttribDC` Gerätekontext verarbeitet alle `CDC` GDI-Attribut aufrufen. Finden Sie in der Regel wird diese zwei Gerätekontexte auf demselben Gerät ein. Im Fall von `CMetaFileDC`, das DC-Attribut wird festgelegt, um **NULL** standardmäßig.  
  
 Erstellen Sie einen zweiten Gerätekontext, die Punkte auf dem Bildschirm, einen Drucker oder Gerät als eine Metadatei, Sie anschließend rufen die `SetAttribDC` Memberfunktion versucht, ordnen Sie den neuen Gerätekontext mit `m_hAttribDC`. GDI-Aufrufe Informationen jetzt geleitet werden, die neue `m_hAttribDC`. Ausgehende Aufrufe von GDI werden zur `m_hDC`, die die Metadatei darstellt.  
  
 Weitere Informationen zu `CMetaFileDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="close"></a>  CMetaFileDC::Close  
 Schließt den Gerätekontext Metadatei und erstellt ein Handle der Windows-Metadatei, die verwendet werden kann, spielt die Metadatei mithilfe der [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) Memberfunktion.  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger **HMETAFILE** , wenn die Funktion erfolgreich ausgeführt, andernfalls wird **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Windows-Metadatei-Handle kann auch verwendet werden, bearbeiten Sie die Metadatei mit Windows-Funktionen wie z. B. [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480).  
  
 Löschen Sie die Metadatei nach der Verwendung durch Aufruf der Windows [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Funktion.  
  
##  <a name="closeenhanced"></a>  CMetaFileDC::CloseEnhanced  
 Schließt eine EMF-Gerätekontext und gibt ein Handle, das eine EMF-Datei bezeichnet.  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle EMF, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann das enhanced Metafile-Handle, das von dieser Funktion zurückgegebenen verwenden, um die folgenden Aufgaben ausführen:  
  
-   Anzeigen eines Bilds in eine erweiterte Metadatei gespeichert  
  
-   Erstellen Sie Kopien der EMF  
  
-   Auflisten Sie, bearbeiten Sie oder kopieren Sie einzelne Datensätze in der EMF  
  
-   Rufen Sie eine optionale Beschreibung des Inhalts der Metadatei aus der EMF-header  
  
-   Rufen Sie eine Kopie des EMF-Headers  
  
-   Rufen Sie eine binäre Kopie der EMF  
  
-   Auflisten der Farben in der Palette optional  
  
-   Konvertieren Sie eine EMF-Datei in eine Windows-Metadatei  
  
 Wenn die Anwendung nicht mehr das Handle EMF benötigt, sollte das Handle durch Aufrufen von Win32 freizugeben **DeleteEnhMetaFile** Funktion.  
  
##  <a name="cmetafiledc"></a>  CMetaFileDC::CMetaFileDC  
 Erstellen einer `CMetaFileDC` Objekt in zwei Schritten.  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zunächst `CMetaFileDC`, rufen Sie anschließend **erstellen**, das erstellt des Windows-Metadatei-Gerätekontexts und fügt es der `CMetaFileDC` Objekt.  
  
##  <a name="create"></a>  CMetaFileDC::Create  
 Erstellen einer `CMetaFileDC` Objekt in zwei Schritten.  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszFilename*  
 Verweist auf eine Null-terminierte Zeichenfolge. Gibt den Dateinamen der Metadatei zu erstellen. Wenn *LpszFilename* ist **NULL**, eine neue in-Memory-Metadatei wird erstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zunächst den Konstruktor `CMetaFileDC`, rufen Sie anschließend **erstellen**, das erstellt des Windows-Metadatei-Gerätekontexts und fügt es der `CMetaFileDC` Objekt.  
  
##  <a name="createenhanced"></a>  CMetaFileDC::CreateEnhanced  
 Erstellt einen Gerätekontext für eine EMF-Datei an.  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>Parameter  
 *pDCRef*  
 Identifiziert ein Referenzgerät für die erweiterte Metadatei an.  
  
 *lpszFileName*  
 Verweist auf eine Null-terminierte Zeichenfolge. Gibt den Dateinamen für die erweiterte Metadatei erstellt werden soll. Wenn dieser Parameter ist **NULL**, EMF ist auf dem Prozessspeicher basierenden und seinen Inhalt verloren gehen, wenn das Objekt zerstört wird oder wenn die Win32 **DeleteEnhMetaFile** Funktion aufgerufen wird.  
  
 *lpBounds*  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Datenstruktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Dimensionen in gibt **HIMETRIC** Einheiten (in Schritten von.01 Millimeter) des Bilds in gespeichert werden die Erweiterte Metadatei.  
  
 *lpszDescription*  
 Verweist auf eine NULL-terminierte Zeichenfolge, die den Namen der Anwendung angibt, die das Bild als auch das Bild Titel erstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle des Gerätekontexts für EMF, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Domänencontroller kann verwendet werden, um eine geräteunabhängige Grafik zu speichern.  
  
 Windows verwendet, das Referenzgerät identifizierte der *pDCRef* Parameter aufzeichnen, die Auflösung und Einheiten des Geräts, auf denen ein Bild ursprünglich angezeigt wurden. Wenn die *pDCRef* Parameter ist **NULL**, das aktuellen Anzeigegerät zu Referenzzwecken verwendet.  
  
 Der linke und obere Mitglieder der `RECT` Datenstruktur verweist die *LpBounds* Parameter muss kleiner sein als die Rechte und untere Elemente bzw. In der Abbildung sind Punkte an den Rändern des Rechtecks enthalten. Wenn *LpBounds* ist **NULL**, die Graphics Device Interface (GDI) berechnet, die Dimensionen der das kleinste Rechteck befindet, die das Bild gezeichnet wird, von der Anwendung einschließen können. Die *LpBounds* -Parameter muss bereitgestellt werden, sofern möglich.  
  
 Die Zeichenfolge verweist die *LpszDescription* Parameter muss zwischen den Namen der Anwendung und den Namen des Bilds ein Null-Zeichen enthalten und muss beendet, und zwei Null-Zeichen, z. B. "XYZ Grafiken Editor\0Bald Eagle\0\0, "\0 darstellt, in dem das Null-Zeichen. Wenn *LpszDescription* ist **NULL**, es gibt keinen entsprechenden Eintrag im EMF-Header.  
  
 Anwendungen verwenden den Domänencontroller, die von dieser Funktion erstellt ein Bild Grafiken in EMF zu speichern. Das Identifizieren von diesem Domänencontroller Handle kann an jeder GDI-Funktion übergeben werden.  
  
 Nach eine Anwendung ein Bild in eine erweiterte Metadatei gespeichert werden, können sie das Bild auf einem beliebigen Ausgabegerät anzeigen, indem Aufrufen der `CDC::PlayMetaFile` Funktion. Wenn das Bild angezeigt wird, verwendet Windows das Rechteck, verweist der *LpBounds* Parameter und die Auflösung Daten vom Gerät Verweis zu positionieren, und das Bild zu skalieren. Der Gerätekontext, der von dieser Funktion zurückgegebenen enthält die gleichen Standardattribute, die neue Domänencontroller zugeordnet.  
  
 Anwendungen müssen die Win32 verwenden **GetWinMetaFileBits** Funktion, um eine erweiterte Metadatei in das ältere Windows Metafile-Format zu konvertieren.  
  
 Verwenden Sie der Dateinamen für die erweiterte Metadatei sollte die. EMF-Erweiterung.  
  
## <a name="see-also"></a>Siehe auch  
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



