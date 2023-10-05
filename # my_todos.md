# my todos

- alright i have the code working somewhat on the glanville notebook
- what i really want to do is:
    - pretrain bert on my data
    - visualize the clustering on the embedding space
    - fine tune the model using my labels
    - assess
- Querstions i have:
    - Will the fine tuning change the embedding space? or is it using the embedding as the inputs like tconv did?
    - can i 'see' somehow how the fine tuning helps?
    -  how can i see the clusters
- FIne tuning:
    - so the way the fine tuning works is that they first use the pretraingn to genreate some embedding space. The pretainer works on the self surpervised task and gets it to a point where it works the best it can.
    - The weights of the trtansformer are then saved. Pretty sure they arenbt compressed into PCA and full dimensionality is used. theres some details here, they peel back some layers here and i htink toss like the last 8.
    - for the fine tuning, a new trnasformer is gnerted, essentailly tyhe same . However instead of like randomly setting the weights, they are preloaded with the weights from the pretrained task. Idk if they freeze any layers or not. But now the output looks much different in that instead of it being mapped to reconstructiuon its mapped to specific antigens (for their case). in the figure it looks like they just stack another net ontop of the bert, but that cant be right
        - the way they're doing classification here is they have the labelled data and they're just pulling random unlabbeled seqs and manually labelling them as non binders. they balance the data like 5:1 'non binders' : 'binders'... they justify the imbalance cause its biologically relevent?


- alright so is the pretrained done on TCRa? yeah this is all done on human data. 
- ok I'm gonna need to pretrain this shit.... only was 88K.

- alright pretrain, save the weights, assume the same level, fine tune. Hem as close possible to current scripts.

    - maybe get some clustering out of the pretrain, that would be nice. 

- from transformers import BertModel
- 