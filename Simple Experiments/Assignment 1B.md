# What are Channels and Kernels?
**Ans**  : Channel is a container of similar things whereas kernels help us to identify those similar things.  
	   For example: `Horizontal lines` is a channel whereas `[[-1,-1,-1],[0,0,0],[1,1,1]]` is a kernel to identify all the horizontal lines in the image.


# Why should we only (well mostly) use 3x3 Kernels?
**Ans**  : We should use 3x3 kernels because:
1. It is odd number of rows and columns which allows us to divide it equally into any section we require.
2. It is smallest size of odd dimension kernel which captures a sequence of information/features which means fast.
3. Nvidia/GPU development has happened to support 3x3 kernels mostly which makes it very fast.


# How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199?
**Ans**  : We need to perform **99** times 3x3 convolution operation.

**Func** : 
```python  
def number_of_operations (x):  
	count = 0  
	while (x != 1):  
		print str (x) + 'x' + str (x), '| 3x3 >',  
		x = x - 2  
		print str (x) + 'x' + str (x),
		print '  '  
		count += 1  
	print count  
```

**Calc** : 
199x199 | 3x3 > 197x197   
197x197 | 3x3 > 195x195   
195x195 | 3x3 > 193x193   
193x193 | 3x3 > 191x191   
191x191 | 3x3 > 189x189   
189x189 | 3x3 > 187x187   
187x187 | 3x3 > 185x185   
185x185 | 3x3 > 183x183   
183x183 | 3x3 > 181x181   
181x181 | 3x3 > 179x179   
179x179 | 3x3 > 177x177   
177x177 | 3x3 > 175x175   
175x175 | 3x3 > 173x173   
173x173 | 3x3 > 171x171   
171x171 | 3x3 > 169x169   
169x169 | 3x3 > 167x167   
167x167 | 3x3 > 165x165   
165x165 | 3x3 > 163x163   
163x163 | 3x3 > 161x161   
161x161 | 3x3 > 159x159   
159x159 | 3x3 > 157x157   
157x157 | 3x3 > 155x155   
155x155 | 3x3 > 153x153   
153x153 | 3x3 > 151x151   
151x151 | 3x3 > 149x149   
149x149 | 3x3 > 147x147   
147x147 | 3x3 > 145x145   
145x145 | 3x3 > 143x143   
143x143 | 3x3 > 141x141   
141x141 | 3x3 > 139x139   
139x139 | 3x3 > 137x137   
137x137 | 3x3 > 135x135   
135x135 | 3x3 > 133x133   
133x133 | 3x3 > 131x131   
131x131 | 3x3 > 129x129   
129x129 | 3x3 > 127x127   
127x127 | 3x3 > 125x125   
125x125 | 3x3 > 123x123   
123x123 | 3x3 > 121x121   
121x121 | 3x3 > 119x119   
119x119 | 3x3 > 117x117   
117x117 | 3x3 > 115x115   
115x115 | 3x3 > 113x113   
113x113 | 3x3 > 111x111   
111x111 | 3x3 > 109x109   
109x109 | 3x3 > 107x107   
107x107 | 3x3 > 105x105   
105x105 | 3x3 > 103x103   
103x103 | 3x3 > 101x101   
101x101 | 3x3 > 99x99   
99x99 | 3x3 > 97x97   
97x97 | 3x3 > 95x95   
95x95 | 3x3 > 93x93   
93x93 | 3x3 > 91x91   
91x91 | 3x3 > 89x89   
89x89 | 3x3 > 87x87   
87x87 | 3x3 > 85x85   
85x85 | 3x3 > 83x83   
83x83 | 3x3 > 81x81   
81x81 | 3x3 > 79x79   
79x79 | 3x3 > 77x77   
77x77 | 3x3 > 75x75   
75x75 | 3x3 > 73x73   
73x73 | 3x3 > 71x71   
71x71 | 3x3 > 69x69   
69x69 | 3x3 > 67x67   
67x67 | 3x3 > 65x65   
65x65 | 3x3 > 63x63   
63x63 | 3x3 > 61x61   
61x61 | 3x3 > 59x59   
59x59 | 3x3 > 57x57   
57x57 | 3x3 > 55x55   
55x55 | 3x3 > 53x53   
53x53 | 3x3 > 51x51   
51x51 | 3x3 > 49x49   
49x49 | 3x3 > 47x47   
47x47 | 3x3 > 45x45   
45x45 | 3x3 > 43x43   
43x43 | 3x3 > 41x41   
41x41 | 3x3 > 39x39   
39x39 | 3x3 > 37x37   
37x37 | 3x3 > 35x35   
35x35 | 3x3 > 33x33   
33x33 | 3x3 > 31x31   
31x31 | 3x3 > 29x29   
29x29 | 3x3 > 27x27   
27x27 | 3x3 > 25x25   
25x25 | 3x3 > 23x23   
23x23 | 3x3 > 21x21   
21x21 | 3x3 > 19x19   
19x19 | 3x3 > 17x17   
17x17 | 3x3 > 15x15   
15x15 | 3x3 > 13x13   
13x13 | 3x3 > 11x11   
11x11 | 3x3 > 9x9   
9x9 | 3x3 > 7x7   
7x7 | 3x3 > 5x5   
5x5 | 3x3 > 3x3   
3x3 | 3x3 > 1x1   

# How are kernels initialized?
**Ans** Kernels are initialized randomly when we start training. Although, there are certain algorithms followed for initialization of kernels and randomness is set to a range.
- Some examples are:
	- Orthogonal: Initializer that generates a random orthogonal matrix.
	- Identity: Initializer that generates the identity matrix.
	- lecun_uniform: LeCun uniform initializer.
	- glorot_normal: Glorot normal initializer, also called Xavier normal initializer.
	- glorot_uniform: Glorot uniform initializer, also called Xavier uniform initializer.
	- he_normal: He normal initializer.
	- lecun_normal: LeCun normal initializer.
	- he_uniform: He uniform variance scaling initializer.


# What happens during the training of a DNN?
**Ans** During the training of a DNN all randomly initialized kernels are assigned weights based on brack propogation and loss so that the last layer always gives the desired output.
