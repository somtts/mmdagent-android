
TARGET   = lib/MMDFiles.a

SOURCES  = src/lib/BulletPhysics.cpp \
           src/lib/CameraController.cpp \
           src/lib/KinematicMotionState.cpp \
           src/lib/MMDFiles_utils.cpp \
           src/lib/MotionController.cpp \
           src/lib/MotionManager.cpp \
           src/lib/PMDBone.cpp \
           src/lib/PMDConstraint.cpp \
           src/lib/PMDFace.cpp \
           src/lib/PMDIK.cpp \
           src/lib/PMDMaterial.cpp \
           src/lib/PMDModel.cpp \
           src/lib/PMDModel_parse.cpp \
           src/lib/PMDModel_render.cpp \
           src/lib/PMDModel_update.cpp \
           src/lib/PMDRigidBody.cpp \
           src/lib/PMDTexture.cpp \
           src/lib/PMDTextureLoader.cpp \
           src/lib/PTree.cpp \
           src/lib/SystemTexture.cpp \
           src/lib/VMD.cpp

OBJECTS  = $(SOURCES:.cpp=.o)

CXX      = gcc
AR       = ar
CXXFLAGS = -Wall -O3 -fomit-frame-pointer -m32 \
           -DMMDFILES_DONTUPDATEMATRICESFORIK \
           -DMMDFILES_DONTSORTORDERFORALPHARENDERING
INCLUDE  = -I ../Library_Bullet_Physics/include \
           -I ../Library_GLee/include \
           -I ../Library_zlib/include \
           -I ../Library_libpng/include \
           -I ../Library_JPEG/include \
           -I src/include

all: $(TARGET)

$(TARGET): $(OBJECTS)
	$(AR) cru $(TARGET) $(OBJECTS)
	cp src/include/*.h include

.cpp.o:
	$(CXX) $(CXXFLAGS) $(INCLUDE) -o $(<:.cpp=.o) -c $<

clean:
	rm -f $(OBJECTS) $(TARGET)
