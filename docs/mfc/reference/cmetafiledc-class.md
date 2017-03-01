---
title: CMetaFileDC-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMetaFileDC
dev_langs:
- C++
helpviewer_keywords:
- CMetaFileDC class
- Windows metafiles [C++]
- metafiles, implementing
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
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
ms.openlocfilehash: 4bff4d7601c4ffbc6fe5cbe73f5e057b79abf1e5
ms.lasthandoff: 02/24/2017

---
# <a name="cmetafiledc-class"></a>CMetaFileDC-Klasse
Implementiert eine Windows-Metadatei, die eine Sequenz von Graphics Device Interface (GDI)-Befehlen enthält, dass Sie wiedergeben können, um ein gewünschtes Bild oder einen Text zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMetaFileDC : public CDC  
```  
  
## <a name="members"></a>Mitglieder  
  
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
|[CMetaFileDC::CreateEnhanced](#createenhanced)|Erstellt einen Metadatei-Gerätekontext für eine EMF-Datei.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Windows-Metadatei zu implementieren, erstellen Sie zunächst ein `CMetaFileDC` Objekt. Aufrufen der `CMetaFileDC` -Konstruktor, rufen Sie dann die [erstellen](#create) Memberfunktion, die ein Windows-Metadatei-Gerätekontext erstellt und fügt es der `CMetaFileDC` Objekt.  
  
 Senden Sie anschließend die `CMetaFileDC` -Objekt die Reihenfolge der `CDC` GDI-Befehle, die Sie möchten zum wiedergeben. Nur die GDI-Befehle, die Ausgabe zu, z. B. erstellen `MoveTo` und `LineTo`, kann verwendet werden.  
  
 Nachdem Sie die gewünschten Befehle an der Metadatei gesendet haben, rufen Sie die **schließen** Memberfunktion, die schließt die Metadatei Gerätekontexte und gibt ein Metadateihandle. Entsorgen Sie dann die `CMetaFileDC` Objekt.  
  
 [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) können Sie die Metadateihandle die Metadatei wiederholt abgespielt. Die Metadatei kann auch bearbeitet werden von Windows-Funktionen wie z. B. [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480), die eine Metadatei auf Festplatte kopiert.  
  
 Wenn die Metadatei nicht mehr benötigt wird, löschen Sie ihn aus dem Speicher mit der [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows-Funktion.  
  
 Sie können auch Implementieren der `CMetaFileDC` Objekt, sodass er behandeln kann beide Aufrufe ausgegeben und Attribut GDI-Aufrufe, z. B. `GetTextExtent`. Solche eine Metadatei ist flexibler und können mehr einfach allgemeine häufig besteht aus einer Mischung aus Ausgabe und Attribut aufrufen GDI-Code wiederverwenden. Die `CMetaFileDC` Klasse erbt, zwei Gerätekontexte `m_hDC` und `m_hAttribDC`, von `CDC`. Die `m_hDC` Gerätekontext verarbeitet alle [CDC](../../mfc/reference/cdc-class.md) GDI Aufrufe ausgegeben und die `m_hAttribDC` Gerätekontext verarbeitet alle `CDC` GDI-Attribut aufrufen. Normalerweise finden Sie diese zwei Gerätekontexte dasselbe Gerät. Im Fall von `CMetaFileDC`, das DC-Attribut wird festgelegt, um **NULL** standardmäßig.  
  
 Erstellen Sie einen zweite Gerätekontext, der Punkte auf dem Bildschirm, einen Drucker oder Gerät als eine Metadatei, Sie dann rufen die `SetAttribDC` Member-Funktion mit den neuen Gerätekontext zuordnen `m_hAttribDC`. GDI-Aufrufe Informationen jetzt geleitet werden, die neue `m_hAttribDC`. GDI-Aufrufe Ausgabe geht an `m_hDC`, die die Metadatei darstellt.  
  
 Weitere Informationen zu `CMetaFileDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="a-nameclosea--cmetafiledcclose"></a><a name="close"></a>CMetaFileDC::Close  
 Schließt den Gerätekontext Metadatei und erstellt ein Windows-Metadatei-Handle, die verwendet werden kann, mithilfe die Metadatei spielen die [CDC::PlayMetaFile](../../mfc/reference/cdc-class.md#playmetafile) Member-Funktion.  
  
```  
HMETAFILE Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger **HMETAFILE** , wenn die Funktion erfolgreich; andernfalls ist **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Windows-Metadatei-Handle kann auch verwendet werden, bearbeiten Sie die Metadatei mit Windows-Funktionen wie z. B. [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480).  
  
 Löschen Sie die Metadatei nach der Verwendung durch Aufruf der Windows [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Funktion.  
  
##  <a name="a-namecloseenhanceda--cmetafiledccloseenhanced"></a><a name="closeenhanced"></a>CMetaFileDC::CloseEnhanced  
 Schließt eine EMF-Gerätekontext, und gibt ein Handle, das eine EMF-Datei identifiziert.  
  
```  
HENHMETAFILE CloseEnhanced();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle des EMF, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung kann das erweiterte Metadatei-Handle, das von dieser Funktion zurückgegebenen verwenden, die folgenden Aufgaben ausführen:  
  
-   Zeigen Sie ein Bild in eine erweiterte Metadatei gespeichert  
  
-   Erstellen Sie Kopien der EMF  
  
-   Auflisten Sie, bearbeiten Sie oder kopieren Sie einzelner Datensätze in der EMF  
  
-   Rufen Sie eine optionale Beschreibung des Inhalts der Metadatei aus der EMF-header  
  
-   Rufen Sie eine Kopie des EMF-Headers  
  
-   Abrufen einer binären Kopie der EMF  
  
-   Auflisten der Farben der optionalen Palette  
  
-   Konvertieren Sie eine EMF-Datei in eine Windows-Metadatei  
  
 Wenn die Anwendung das EMF-Handle nicht mehr erforderlich ist, sollten sie das Handle freigeben, durch Aufruf der Win32 **DeleteEnhMetaFile** Funktion.  
  
##  <a name="a-namecmetafiledca--cmetafiledccmetafiledc"></a><a name="cmetafiledc"></a>CMetaFileDC::CMetaFileDC  
 Erstellen einer `CMetaFileDC` Objekt in zwei Schritten.  
  
```  
CMetaFileDC();
```  
  
### <a name="remarks"></a>Hinweise  
 Zunächst rufen `CMetaFileDC`, rufen Sie dann **erstellen**, die den Windows-Metadatei-Gerätekontext erstellt und fügt es der `CMetaFileDC` Objekt.  
  
##  <a name="a-namecreatea--cmetafiledccreate"></a><a name="create"></a>CMetaFileDC::Create  
 Erstellen einer `CMetaFileDC` Objekt in zwei Schritten.  
  
```  
BOOL Create(LPCTSTR lpszFilename = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszFilename*  
 Zeigt auf eine Null-terminierte Zeichenfolge. Gibt den Dateinamen der Metadatei erstellen. Wenn *LpszFilename* ist **NULL**, eine neue in-Memory-Metadatei wird erstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Zunächst rufen Sie den Konstruktor `CMetaFileDC`, rufen Sie dann **erstellen**, die den Windows-Metadatei-Gerätekontext erstellt und fügt es der `CMetaFileDC` Objekt.  
  
##  <a name="a-namecreateenhanceda--cmetafiledccreateenhanced"></a><a name="createenhanced"></a>CMetaFileDC::CreateEnhanced  
 Erstellt einen Gerätekontext für eine EMF-Datei.  
  
```  
BOOL CreateEnhanced(
    CDC* pDCRef,  
    LPCTSTR lpszFileName,  
    LPCRECT lpBounds,  
    LPCTSTR lpszDescription);
```  
  
### <a name="parameters"></a>Parameter  
 `pDCRef`  
 Identifiziert ein Referenz-Gerät für die erweiterte Metadatei an.  
  
 `lpszFileName`  
 Zeigt auf eine Null-terminierte Zeichenfolge. Gibt den Dateinamen für die erweiterte Metadatei erstellt werden. Wenn dieser Parameter **NULL**, EMF wird Arbeitsspeicher auf Grundlage und seinen Inhalt verloren gehen, wenn das Objekt zerstört wird oder wenn die Win32 **DeleteEnhMetaFile** -Funktion aufgerufen wird.  
  
 `lpBounds`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Datenstruktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Dimensionen in gibt **HIMETRIC** Einheiten (in Schritten von.01 Millimeter) des Bilds in der erweiterten Metadatei gespeichert werden.  
  
 `lpszDescription`  
 Zeigt auf eine NULL-terminierte Zeichenfolge, die den Namen der Anwendung angibt, die das Bild als auch das Bild Titel erstellt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den Gerätekontext für EMF, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Domänencontroller kann verwendet werden, ein Bild geräteunabhängige speichern.  
  
 Windows verwendet das Referenz-Gerät, das anhand der `pDCRef` Parameter zum Aufzeichnen der Lösung und Einheiten des Geräts auf dem Bild ursprünglich angezeigt wurde. Wenn die `pDCRef` Parameter ist **NULL**, das aktuellen Anzeigegerät als Referenz verwendet.  
  
 Die linken und oberen Mitglieder der `RECT` -Datenstruktur zeigt die `lpBounds` Parameter muss kleiner sein als die Rechte und untere Elemente bzw.. Punkte entlang der Ränder des Rechtecks sind in der Abbildung enthalten. Wenn `lpBounds` ist **NULL**, die Graphics Device Interface (GDI) berechnet die Dimensionen des kleinsten Rechtecks, die das Bild gezeichnet wird, von der Anwendung einschließen können. Der `lpBounds` -Parameter muss bereitgestellt werden, soweit möglich.  
  
 Die Zeichenfolge zeigt die `lpszDescription` Parameter muss zwischen der Anwendung und den Namen des Bilds ein Null-Zeichen enthalten und muss mit zwei Null-Zeichen enden – z. B. "XYZ Grafiken Editor\0Bald Eagle\0\0," \0, in dem das Null-Zeichen darstellt. Wenn `lpszDescription` ist **NULL**, es gibt keinen entsprechenden Eintrag im EMF-Header.  
  
 Applications verwenden den DC, der von dieser Funktion erstellt ein Bild Grafiken in EMF zu speichern. Das Handle, das diesen Domänencontroller identifizieren kann auf jede GDI-Funktion übergeben werden.  
  
 Nach eine Anwendung ein Bild in eine erweiterte Metadatei gespeichert werden, können sie das Bild auf jedem Ausgabegerät anzeigen, indem Sie Aufrufen der `CDC::PlayMetaFile` Funktion. Wenn das Bild angezeigt wird, verwendet Windows das Rechteck auf die der `lpBounds` -Parameter und die Auflösung Daten vom Gerät Verweis positionieren und Skalieren das Bild. Der Gerätekontext, der von dieser Funktion zurückgegebenen enthält die gleichen Standardattribute neue Domänencontroller zugeordnet.  
  
 Clientanwendungen müssen die Win32 verwenden **GetWinMetaFileBits** Funktion, um eine erweiterte Metadatei in älteren Windows Metafile Format zu konvertieren.  
  
 Verwenden Sie der Dateinamen für die erweiterte Metadatei sollte die. EMF-Erweiterung.  
  
## <a name="see-also"></a>Siehe auch  
 [CDC-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




