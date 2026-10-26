# Cutting a Tree into Stubs
**트리를 미연결 링크로 쪼개어 다시 잇기**

An interactive demo of the configuration model, part of the [interactive demos](https://lshlj82.github.io/netsci-course-GNU/) for *Network Science* (네트워크 과학) in the Department of Physics, Gyeongsang National University. It is a supplement (9′) to demo 9, [Network models](https://lshlj82.github.io/network-models/).

**Live page:** https://lshlj82.github.io/stub-rewiring/

Created by Claude Opus 5.5, based on the slide for Prof. Laurent Hébert-Dufresne’s talk at KIAS on September 29, 2022.
2022년 9월 29일 고등과학원(KIAS)에서 열린 Laurent Hébert-Dufresne 교수님의 강연 슬라이드를 바탕으로 Claude Opus 5.5가 만들었습니다.

## What it shows · 내용

The slide puts two networks side by side under the caption "Description: degree distribution". On the left is a Cayley tree: a central node with three neighbors, every other internal node with one parent and two children, six generations in all. That gives 190 nodes and 189 links, with 94 nodes of degree 3 and 96 leaves of degree 1. On the right is a configuration-model network with exactly the same degree sequence: a giant component of 158 nodes with 14 independent loops, two stars with three leaves each, and 12 isolated pairs.

Both networks were read off the photo of the slide link by link. Nodes were located by color and links found as straight dark lines between them; where a line could be read in more than one way, the rule that each orange node has three links and each navy node one decided it. The pair at the bottom right that the presenter’s hand partly covers is read as an isolated pair. The left reading is the Cayley tree exactly, and the right reading gives all 190 nodes their degrees.

The demo turns one into the other in five steps:

1. **Tree.** The Cayley tree from the slide.
2. **Cut.** Every link is cut at its midpoint, leaving two stubs (half-links). Each node keeps as many stubs as it had links.
3. **Sort stubs.** The nodes are lined up by degree: 94 with three stubs and 96 with one, 378 stubs in total.
4. **Rewire.** The stubs are joined in pairs. With the wiring set to *as on the slide*, they are joined exactly as the links run on the right of the slide; with *new random*, they are matched uniformly at random, redrawing any matching that would create a self-loop or a double link.
5. **Relax.** With the slide’s wiring, every node moves to its place on the right of the slide. With a random wiring, a force-directed layout lets the new network find its shape.

The slide does not say which node on the left becomes which node on the right, so nodes of equal degree are matched at random; only the links are the slide’s.

A side panel shows the degree distribution throughout. The bars (stubs per node) never move. The dots (links attached right now) drop to *k* = 0 when the tree is cut and climb back onto the bars as the stubs are rewired. A table compares the tree with the current network: links, components, independent loops *m* − *n* + *c*, the largest component, and isolated pairs. Nodes can be colored by degree, as on the right of the slide, or by generation, as on the left.

The page text also works out two expectations for this degree sequence: about 4560/377 ≈ 12 isolated leaf–leaf pairs (the slide has 12), and, since ⟨*k*²⟩ − 2⟨*k*⟩ = 0.98 > 0 (Molloy–Reed), a giant component holding about 81% of the nodes, or about 154 of 190 (the slide has 158).

슬라이드에는 “Description: degree distribution”이라는 설명과 함께 두 네트워크가 나란히 있습니다. 왼쪽은 중심 노드에 이웃이 셋, 나머지 내부 노드는 부모 하나에 자식 둘을 가지며 여섯 세대에서 멈추는 케일리 트리로, 노드 190개(연결선수 3인 노드 94개, 잎 96개)와 링크 189개로 이루어집니다. 오른쪽은 같은 연결선수열로 만든 구성 모형 네트워크입니다. 두 네트워크 모두 슬라이드 사진에서 링크를 하나하나 읽어 냈습니다. 데모는 트리의 모든 링크를 반으로 잘라 미연결 링크 378개를 만들고, 이를 슬라이드 오른쪽 네트워크 그대로 또는 새로운 무작위 짝으로 다시 이은 뒤 펼쳐서, 연결선수 분포는 그대로인데 고리와 고립된 쌍, 거대 연결 덩어리가 생기는 과정을 보여 줍니다.

## About the page · 페이지 소개

The page is a single `index.html` with no build step and no libraries, plus `slide.jpg`, a photo of the slide shown under “What the slide shows”. It supports light and dark mode (the choice is shared with the other course demos), adapts to phone screens, and steps through the stages without animation for visitors who have reduced motion turned on.

빌드 과정이나 라이브러리 없이 `index.html` 파일 하나와 슬라이드 사진 `slide.jpg`로 이루어져 있습니다. 밝은 화면과 어두운 화면을 모두 지원하고(선택은 다른 교과목 데모와 공유됩니다), 휴대폰 화면에 맞게 바뀌며, 동작 줄이기 설정을 켠 방문자에게는 애니메이션 없이 단계별 결과를 보여 줍니다.
