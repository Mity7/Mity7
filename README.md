class A:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f"I am a {self.name}"

    def dl(self):
        pass

    def Lt(self):
        pass

class B(A):
    def dl(self):
        print("Method dl in class B")

class C(A):
    def dl(self):
        print("Method dl in class C")

class D(C):
    def dl(self):
        print("Method dl in class D")

class E(B, D):
    def dl(self):
        print("Method dl in class E")

class Chart:
    def __init__(self):
        self.elements = []

    def add(self, element):
        self.elements.append(element)

    def __str__(self):
        return f"Chart with {len(self.elements)} elements"

    def getter(self):
        return self.elements

    def setter(self, elements):
        self.elements = elements

# Usage
b = B("B")
c = C("C")
d = D("D")
e = E("E")

chart = Chart()
chart.add(b)
chart.add(c)
chart.add(d)
chart.add(e)

print(chart)
for element in chart.getter():
    print(element)
    element.dl()