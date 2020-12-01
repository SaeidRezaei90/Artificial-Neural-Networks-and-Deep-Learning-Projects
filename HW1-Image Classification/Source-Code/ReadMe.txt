Important parameters:
SEED =42
img_h=384, img_w=384
lr=1e-4, except for fine_tuning which is 1e-5
EarlyStopping(monitor='val_loss',Patience=5)
epochs=30

The best code is  TOSAF.ipynb

before starting write:
pip uninstall keras-preprocessing
pip install git+https://github.com/keras-team/keras-preprocessing.git


depending on computational capability of your device you can un/comment
the following line in TOSAF.ipynb:

X=tf.keras.layers.GlobalAVeragePooling2D()(x)