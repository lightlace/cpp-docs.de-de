---
title: CMFCCmdUsageCount Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0db24894777170d2860ba8d1639fd44e3893732a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount-Klasse
Überwacht die Verwendungsanzahl der Windows-Meldungen, z. B. wenn der Benutzer ein Element aus einem Menü auswählt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Standardkonstruktor|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Inkrementiert um eins der Zähler, der den angegebenen Befehl zugeordnet ist.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Ruft die Verwendungsanzahl der, die der angegebenen Befehls-ID zugeordnet ist.|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Bestimmt, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt hat.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Bestimmt, ob der angegebene Befehl häufig verwendet wird.|  
|[CMFCCmdUsageCount::Reset](#reset)|Löscht die Verwendungsanzahl der aller Befehle.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Legt die Werte der freigegebenen `CMFCCmdUsageCount` Klassendatenmember.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|`m_CmdUsage`|Ein `CMap` -Objekt, das ihre Verwendungszähler Befehle zugeordnet.|  
|`m_nMinUsagePercentage`|Die minimale Auslastung in Prozent für einen Befehl aus, um häufig verwendet werden.|  
|`m_nStartCount`|Der Start-Zähler, der verwendet wird, um zu bestimmen, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt hat.|  
|`m_nTotalUsage`|Die Anzahl der Befehle alle nachverfolgten.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCCmdUsageCount` -Klasse ordnet jede numerische Windows-Nachrichten-ID, einen Indikator für 32-Bit-Ganzzahl ohne Vorzeichen. `CMFCToolBar`Mithilfe dieser Klasse häufig verwendete Symbolleistenelemente angezeigt. Weitere Informationen zu `CMFCToolBar`, finden Sie unter [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md).  
  
 Sie können beibehalten `CMFCCmdUsageCount` -Klasse Daten zwischen den Ausführungen des Programms. Verwenden der [CMFCCmdUsageCount::Serialize](#serialize) -Methode zum Serialisieren von Klassenmemberdaten und [CMFCCmdUsageCount::SetOptions](#setoptions) Methode, um freigegebene Elementdaten einzurichten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>CMFCCmdUsageCount::AddCmd  
 Inkrementiert um eins der Zähler, der den angegebenen Befehl zugeordnet ist.  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `uiCmd`|Gibt den Befehl Zähler erhöht.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt einen neuen Eintrag zur Zuordnung Struktur des Befehls Anzahlen `m_CmdUsage`, wenn der Eintrag nicht bereits vorhanden ist.  
  
 Diese Methode bewirkt nichts in den folgenden Fällen:  
  
-   Die Symbolleiste-Framework ist im Anpassungsmodus (die [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) Methode gibt einen Wert ungleich NULL zurück).  
  
-   Der Befehl bezieht sich auf ein Untermenü oder Menü als Trennzeichen ( `uiCmd` gleich 0 oder -1).  
  
- `uiCmd`bezieht sich auf einen Standardbefehl (globalen `IsStandardCommand` Funktion gibt einen Wert ungleich NULL zurück).  
  
##  <a name="getcount"></a>CMFCCmdUsageCount::GetCount  
 Ruft die Verwendungsanzahl der, die der angegebenen Befehls-ID zugeordnet ist.  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `uiCmd`|Die ID des Leistungsindikators Befehl abrufen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verwendungsanzahl der, die der angegebenen Befehls-ID zugeordnet ist.  
  
##  <a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation  
 Bestimmt, ob dieses Objekt die Mindestmenge an Überwachungsdaten erhalten hat.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn dieses Objekt die Mindestmenge an Überwachungsdaten erhalten hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL zurück, wenn die Gesamtanzahl `m_nTotalUsage`, der alle nachverfolgten Befehle ist gleich oder größer als die anfängliche Anzahl `m_nStartCount`. Standardmäßig legt das Framework die anfängliche Anzahl 0. Sie können diesen Wert überschreiben, indem Sie mit der [CMFCCmdUsageCount::SetOptions](#setoptions) Methode.  
  
 Diese Methode wird verwendet, indem [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) bestimmt, ob alle im Kontextmenü verfügbaren Befehle angezeigt.  
  
##  <a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 Bestimmt, ob der angegebene Befehl häufig verwendet wird.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `uiCmd`|Gibt den Befehl aus, um zu überprüfen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Befehl häufig verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt 0 zurück, wenn die gesamte Befehlssyntax `m_nTotalUsage`, ist 0. Diese Methode zurückgibt, andernfalls ungleich NULL, wenn der Prozentsatz, der der angegebene Befehl dient, den Mindestprozentsatz übersteigt `m_nMinUsagePercentage`. Standardmäßig legt das Framework den Mindestprozentsatz bis 5. Sie können diesen Wert überschreiben, indem Sie mit der [CMFCCmdUsageCount::SetOptions](#setoptions) Methode. Wenn Sie der Mindestprozentsatz 0 ist, gibt diese Methode ungleich NULL, wenn die angegebene Anzahl größer als 0 ist.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) verwendet diese Methode, um zu bestimmen, ob ein Befehl nur selten verwendet wird.  
  
##  <a name="reset"></a>CMFCCmdUsageCount::Reset  
 Löscht die Verwendungsanzahl der aller Befehle.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, deaktivieren Sie alle Einträge aus der Struktur Zuordnung Befehl Anzahlen `m_CmdUsage`, und die gesamte Befehlssyntax zurücksetzen `m_nTotalUsage`, Zähler auf 0.  
  
##  <a name="serialize"></a>CMFCCmdUsageCount::Serialize  
 Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `ar`|Ein `CArchive` zu von oder zu serialisierende Objekt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode serialisiert die Map-Struktur der Befehl Anzahlen `m_CmdUsage`, und die gesamte Befehlssyntax `m_nTotalUsage`, Leistungsindikator aus oder in der angegebenen Archiv.  
  
 Beispiele für die Serialisierung finden Sie unter [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="setoptions"></a>CMFCCmdUsageCount::SetOptions  
 Legt die Werte der freigegebenen `CMFCCmdUsageCount` Klassendatenmember.  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `nStartCount`|Die anfängliche Anzahl neuer alle nachverfolgten Befehle.|  
|[in] `nMinUsagePercentage`|Die neue minimale Auslastung in Prozent.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist, `FALSE` Wenn die `nMinUsagePercentage` Parameter ist größer als oder gleich 100.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode wird die freigegebene `CMFCCmdUsageCount` Klassendatenmember `m_nStartCount` und `m_nMinUsagePercentage` auf `nStartCount` und `nMinUsagePercentage`zugeordnet. `m_nStartCount`wird verwendet, durch die [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) Methode, um zu bestimmen, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt hat. `m_nMinUsagePercentage`wird verwendet, durch die [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) Methode, um zu bestimmen, ob ein bestimmter Befehl häufig verwendet wird.  
  
 In Debugbuilds diese Methode generiert ein Assertionsfehler ausgelöst, wenn die `nMinUsagePercentage` Parameter ist größer als oder gleich 100.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)
