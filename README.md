# Session-1-Assignment

## Question -1) What are Channels and Kernels?
### Answer.) CHANNELS -

In simple terms channels refer to a bag of fixed type of information.And by that we mean to say that suppose you have an image which consist of various things and by some criteria we fix that some of the particular things belong to a fixed type of information,for example if we want to give all the letters "B" in a image of text some special importance then we will say that a layer consisting of all the "B" only will be called as a channel 
  
  In a funny way let us suppose that there is a disease in which you can only see all the "B's" of the world and now I bring a textual image in front of you ---> Now what you will be seeing is what we call a channel because it has only one type of information that is "B"
     
### Kernels 
   
  Now the important question is how do you get all those "B's" separated out in a layer.That is something which is done using a MAtrix which has a special and cool name called as KERNEL. Keep in mind that KERNEL is just a 3*3 matrix and nothing fancy.Kernel are also called as Feature Extractor.
  
  In a funny way the infection which allows you to see only the "B's" is what we call as kernel.There might be some other infections which will allow you to see only "M"(lets say) then they will be called as the kernels for their respective channels which is "M".
  
  
## Question -2) Why should we (nearly) always use 3x3 kernels?
### Answer.) 

Firstly let us see why can't we use a kernel which is of the order n*n where n is even --> the answer to this question is that there is no symmetry in case of kernels with even orders hence we use kernels of the type n*n only where n is an odd number.

Now the question arises that why to use only 3*3 and not 5*5 or 7*7* or 9*9 --> Then the simple answer to that is "EVERY 5*5 KERNEL CAN BE FORMED USING 2 3*3 KERNELS AND EVERY 7*7 KERNEL CAN BE FORMED USING 3 3*3 KERNELS"

Now the question might arise up that instead of using 2 3*3 kernels why can't we use a single 5*5 kernel ? --> What happens in 5*5 kernel is that we have 25 parameters(Why? Pick up a pen and paper and try to figure out) while if we consider 2 3*3 kernels then in total we will have 18(9+9) parameters and this difference starts increasing exponentially hence the best suited kernel for most of the cases is 3*3 only.

## Question -3.) How many times to we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 199x199 > 197x197...)

### Answer -> 

199 * 199 -->197 * 197 -->195 * 195 -->193 * 193 -->191 * 191 -->189 * 189 -->187 * 187 -->185 * 185 -->183 * 183 -->181 * 181 -->179 * 179 -->177 * 177 -->175 * 175 -->173 * 173 -->171 * 171 -->169 * 169 -->167 * 167 -->165 * 165 -->163 * 163 -->161 * 161 -->159 * 159 -->157 * 157 -->155 * 155 -->153 * 153 -->151 * 151 -->149 * 149 -->147 * 147 -->145 * 145 -->143 * 143 -->141 * 141 -->139 * 139 -->137 * 137 -->135 * 135 -->133 * 133 -->131 * 131 -->129 * 129 -->127 * 127 -->125 * 125 -->123 * 123 -->121 * 121 -->119 * 119 -->117 * 117 -->115 * 115 -->113 * 113 -->111 * 111 -->109 * 109 -->107 * 107 -->105 * 105 -->103 * 103 -->101 * 101 -->99 * 99 -->97 * 97 -->95 * 95 -->93 * 93 -->91 * 91 -->89 * 89 -->87 * 87 -->85 * 85 -->83 * 83 -->81 * 81 -->79 * 79 -->77 * 77 -->75 * 75 -->73 * 73 -->71 * 71 -->69 * 69 -->67 * 67 -->65 * 65 -->63 * 63 -->61 * 61 -->59 * 59 -->57 * 57 -->55 * 55 -->53 * 53 -->51 * 51 -->49 * 49 -->47 * 47 -->45 * 45 -->43 * 43 -->41 * 41 -->39 * 39 -->37 * 37 -->35 * 35 -->33 * 33 -->31 * 31 -->29 * 29 -->27 * 27 -->25 * 25 -->23 * 23 -->21 * 21 -->19 * 19 -->17 * 17 -->15 * 15 -->13 * 13 -->11 * 11 -->9 * 9 -->7 * 7 -->5 * 5 -->3 * 3 -->1 * 1

 ####  We need to perform convolutions 99 times in total in order to reach from 199*199 --> 1*1.

## Question -4.) How are kernels initialized? 

### Answer.) 

Kernels are most of the times initialized using Random values from Normal Gaussian Distribution.Although there are various research paper which use different methods of initialization of the kernels but most of the time selecting random values from normal gaussian distribution is prefered.This is because initialization is not the only thing which controls the entire model.Training also manages lot of aspects of changing these values of the kernel to best suit our accuracy.

## Querstion -5) What happens during the training of a DNN?

### Answer.) 

When we randomly initialize the kernel values then that thing sounds ofcourse weird because everyone will be getting totally different outcomes for the same model everytime they run. Now what happens for a DNN is training and that is the most time taking process in the entire DNN cycle. What in short happens in training a DNN is that the kernel values which we initialized randomly are now changed slowly based on the output we received using the previous Kernel values and they are changed in such a way that we get accuracy better than before not immediately after it but yes after a couple of running our networks.

And slowly what happens is that for some particular vlaues of our kernel our model stops showing improvement in accuracy any more and there we say that the training is complete now and the kernel values for that accuracy are our final kernel values.

##### In short learning the kernel values or the weights in order to get good accuracy is what we call as training.
