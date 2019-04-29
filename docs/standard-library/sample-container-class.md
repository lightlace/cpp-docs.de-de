---
title: Sample Container-Klasse
ms.date: 11/04/2016
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
ms.openlocfilehash: dbfa076756b9e4829898d38e0277ad90106ba579
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410992"
---
# <a name="sample-container-class"></a>Sample Container-Klasse

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Beschreibt ein Objekt, das eine Elementsequenz variabler Länge Sequenz von Elementen, in der Regel des Typs steuert `Ty`. Die Folge ist unterschiedlich gespeichert, abhängig vom tatsächlichen Container.

Ein Containerkonstruktor oder eine Memberfunktion finden möglicherweise Anlass, den Konstruktor **Ty**(**const Ty &**) oder die Funktion **Ty::operator =**(**const Ty &**) aufzurufen. Wenn solch ein Aufruf eine Ausnahme auslöst, ist das Containerobjekt verpflichtet, seine Integrität beizubehalten, und jede Ausnahme, die es entdeckt, erneut auslösen. Sie können ein Containerobjekt sicher austauschen, zuweisen, löschen oder zerstören, nachdem es eine dieser Ausnahmen auslöst. Im Allgemeinen jedoch können Sie den Zustand der vom Containerobjekt kontrollierten Sequenz andernfalls nicht vorhersagen.

Einige zusätzliche Vorsichtsmaßnahmen:

- Wenn der Ausdruck `~Ty` eine Ausnahme auslöst, die der resultierende Status des Containerobjekts ist nicht definiert.

- Wenn der Container ein Zuweisungsobjekt speichert *al*, und *al* löst eine Ausnahme aufgrund eines Aufrufs von `al.allocate`, der resultierende Status des Containerobjekts nicht definiert ist.

- Wenn der Container ein Funktionsobjekt *comp* speichert, um zu bestimmen, wie die kontrollierte Sequenz sortiert wird und *comp* eine beliebige Ausnahme auslöst, ist der resultierende Status des Containerobjekts nicht definiert.

Die Containerklassen, die von der C++-Standardbibliothek definiert werden, erfüllen noch weitere Anforderungen, wie in den folgenden Abschnitten beschrieben.

Die Containervorlagenklasse [list](../standard-library/list-class.md) enthält deterministisches und nützliches Verhalten, auch bei den oben beschriebenen Ausnahmen. Wenn beispielsweise eine Ausnahme während des Einfügens von einem oder mehreren Elementen ausgelöst wird, bleibt der Container unverändert, und die Ausnahme wird erneut ausgelöst.

Für *alle* Containerklassen, die von C++-Standardbibliothek definiert werden, wenn eine Ausnahme, während die folgenden Memberfunktionen aufgerufen ausgelöst wird `insert`, `push_back`, oder `push_front`, der Container unverändert, und die Ausnahme wird erneut ausgelöst.

Für *alle* Containerklassen, die von C++-Standardbibliothek definiert werden, während die folgenden Memberfunktionen aufgerufen wird keine Ausnahme ausgelöst: `pop_back`, `pop_front`.

Die Memberfunktion [erase](../standard-library/container-class-erase.md) löst eine Ausnahme nur aus, wenn ein Kopiervorgang (Zuweisung oder Copy-Konstruktion) eine Ausnahme auslöst.

Darüber hinaus wird keine Ausnahme ausgelöst, während des Kopiervorgangs eines Iterators, der von einer Memberfunktion zurückgegeben wird.

Die Memberfunktion [swap](../standard-library/container-class-swap.md) macht zusätzliche Zusagen für *alle* Containerklassen, die von der C++-Standardbibliothek definiert werden:

- Die Memberfunktion löst eine Ausnahme nur dann aus, wenn der Container eine Zuweisungsobjekt al speichert und `al` löst beim Kopiervorgang eine Ausnahme aus.

- Verweise, Zeiger und Iteratoren, die getauschte Elemente der gesteuerten Sequenzen anzeigen, bleiben gültig.

Ein Objekt einer Containerklasse, die von der C++-Standardbibliothek definiert wird, reserviert Speicher und gibt ihn für die gesteuerte Sequenz frei, die sie durch ein gespeichertes Objekt vom Typ `Alloc` kontrolliert. Dieser ist gewöhnlich ein Vorlagenparameter. Solches Zuweisungsobjekt muss die gleiche externe Schnittstelle wie ein Objekt der Klasse haben `allocator<Ty>`. Insbesondere `Alloc` muss denselben Typ wie `Alloc::rebind<value_type>::other`

Für *alle* Containerklassen, die von C++-Standardbibliothek, die Member-Funktion definiert `Alloc get_allocator const;` gibt eine Kopie des gespeicherten Zuordnungsobjekts zurück. Beachten Sie, dass das gespeicherte Zuweisungsobjekt *nicht* kopiert wird, wenn das Containerobjekt zugewiesen wird. Alle Konstruktoren initialisieren, die in gespeicherten Wert `allocator`zu `Alloc` , wenn der Konstruktor keine Zuweisungsparameter enthält.

Entsprechend dem C++-Standard kann eine Container-Klasse, die die C++-Standardbibliothek definiert, folgendes darstellen:

- Alle Objekte der Klasse `Alloc` sind beim Vergleich gleich.

- Typ `Alloc::const_pointer` ist identisch mit `const Ty *`.

- Typ `Alloc::const_reference` ist identisch mit `const Ty&`.

- Typ `Alloc::pointer` ist identisch mit `Ty *`.

- Typ `Alloc::reference` ist identisch mit `Ty&`.

In dieser Implementierung treffen Container jedoch nicht solche vereinfachende Annahmen. Daher arbeiten sie ordnungsgemäß mit Zuweisungsobjekten, die ehrgeiziger sind:

- Alle Objekte der `Alloc`-Klasse werden beim Vergleich nicht gleich abschneiden. (Sie können mehrere Speicherpools verwalten.)

- Typ `Alloc::const_pointer` muss nicht identisch sein `const Ty *`. (Ein const-Zeiger kann eine Klasse sein.)

- Typ `Alloc::pointer` muss nicht identisch sein `Ty *`. (Ein Zeiger kann eine Klasse sein.)

## <a name="requirements"></a>Anforderungen

**Header**: \<sample container>

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)<br/>
