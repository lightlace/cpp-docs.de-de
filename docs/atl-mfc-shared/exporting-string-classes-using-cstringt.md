---
title: Exportieren von Zeichenfolgenklassen mit CStringT | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CStringT class, exporting strings
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2d77516ae53b0ee1c4f39e4d8f095848aa00acc
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889970"
---
# <a name="exporting-string-classes-using-cstringt"></a>Exportieren von Zeichenfolgenklassen mit CStringT

In der Vergangenheit MFC-Entwickler abgeleitet haben `CString` eigene Zeichenfolgenklassen spezialisiert werden kann. In Microsoft Visual C++ .NET (MFC-8.0) die [CString](../atl-mfc-shared/using-cstring.md) Klasse wurde ersetzt durch eine Klasse namens [CStringT](../atl-mfc-shared/reference/cstringt-class.md). Dies mehrere Vorteile zur Verfügung:

- Es zulässig, dass die MFC-Bibliothek `CString` Klasse, die in ATL-Projekte ohne in den größeren statischen MFC-Bibliothek oder DLL verknüpfen.

- Mit dem neuen `CStringT` Vorlagenklasse, die Sie anpassen können `CString` -Verhaltens mithilfe der Vorlagenparameter, mit denen Zeichenmerkmale, ähnlich wie die Vorlagen in der C++-Standardbibliothek angegeben.

- Wenn Sie eigene String-Klasse aus einer DLL exportieren `CStringT`, der Compiler automatisch exportiert die `CString` Basisklasse. Da `CString` selbst eine Vorlagenklasse, ist es instanziiert werden vom Compiler bei verwendet, es sei denn, die dem Compiler bekannt ist, die `CString` aus einer DLL importiert wird. Wenn Sie Projekte von Visual C++ 6.0 auf Visual c++.NET migriert haben, Sie haben eventuell bereits Symbol Linkerfehler für ein mehrfach definiertes `CString` aufgrund der Konflikte zwischen der `CString` aus einer DLL und die lokal instanziierte Version importiert. Der richtige Weg zu diesem Zweck wird unten beschrieben.

Das folgende Szenario führt dazu, dass der Linker symbolfehler für mehrfach definiertes Klassen erstellt. Angenommen, Sie exportieren eine `CString`-abgeleitete Klasse (`CMyString`) aus einer MFC-Erweiterungs-DLL:

[!code-cpp[NVC_MFC_DLL#6](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_1.cpp)]

Der Consumercode verwendet eine Kombination von `CString` und `CMyString`. "MyString.h" befindet sich nicht in der vorkompilierten Headerdatei und eine Verwendung von `CString` verfügt nicht über `CMyString` sichtbar.

Angenommen, Sie verwenden die `CString` und `CMyString` Klassen in separaten Quelldateien Source1.cpp und Source2.cpp. In Source1.cpp, verwenden Sie `CMyString` und #include MyString.h. In Source2.cpp, verwenden Sie `CString`, jedoch nicht #include MyString.h. In diesem Fall der Linker wird der Adresssyntax `CStringT` wird mehrfach definiert. Ursache hierfür ist `CString` wird sowohl von der DLL, die exportiert importiert `CMyString`, und lokal instanziiert, indem der Compiler über die `CStringT` Vorlage.

Um dieses Problem zu beheben, führen Sie folgende Schritte aus:

Exportieren Sie `CStringA` und `CStringW` (und die erforderlichen Basisklassen) von MFC90. DLL. Projekte, die MFC enthalten verwendet immer die MFC-DLL exportiert `CStringA` und `CStringW`, wie in früheren MFC-Implementierungen.

Erstellen Sie dann auf einer exportierbaren abgeleiteten Klasse mithilfe der `CStringT` Vorlage als `CStringT_Exported` finden Sie nachstehend, z.B.:

[!code-cpp[NVC_MFC_DLL#7](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_2.cpp)]

Ersetzen Sie im AfxStr.h, die vorherige `CString`, `CStringA`, und `CStringW` Typdefinitionen wie folgt:

[!code-cpp[NVC_MFC_DLL#8](../atl-mfc-shared/codesnippet/cpp/exporting-string-classes-using-cstringt_3.cpp)]

Es gibt mehrere Einschränkungen zu beachten:

- Exportieren Sie keine `CStringT` selbst da dies nur ATL-Projekte so exportieren Sie ein spezielles verursacht `CStringT` Klasse.

- Verwenden einer exportierbaren Klasse aus `CStringT` minimiert wird, müssen erneut implementieren `CStringT` Funktionalität. Zusätzlicher Code ist die Weiterleitung von Konstruktoren zum beschränkt die `CStringT` Basisklasse.

- `CString`, `CStringA`, und `CStringW` darf nur markiert werden `__declspec(dllexport/dllimport)` gemeinsam genutzte beim Erstellen mit einem MFC-DLL. Wenn Sie eine Verknüpfung mit einer statischen MFC-Bibliothek erstellen möchten, sollten Sie diese Klassen nicht markieren, als exportiert; andernfalls, die interne Verwendung von `CString`, `CStringA`, und `CStringW` in DLLs wird Markierung `CString` als ebenfalls exportiert.

## <a name="related-topics"></a>Verwandte Themen

[CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)

## <a name="see-also"></a>Siehe auch

[Verwenden von CStringT](../atl-mfc-shared/using-cstringt.md)<br/>
[Verwenden von CString](../atl-mfc-shared/using-cstring.md)

