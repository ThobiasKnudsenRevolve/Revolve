# Set paths to BGFX directories (update these paths based on your setup)
BGFX_DIR = /home/kali/dev/libraries/bgfx/bgfx             # Update this to the actual path of the BGFX folder
BGFX_BUILD_DIR = $(BGFX_DIR)/build   # Update this if your build output is in a different location

# Compiler and flags
CXX = g++
CXXFLAGS = -I$(BGFX_DIR)/include/bgfx -I$(BGFX_DIR)/bx/include -I$(BGFX_DIR)/bimg/include
LDFLAGS = -L$(BGFX_BUILD_DIR) -lbgfx -lbx -lbimg -lGL -ldl -lpthread

# Source files
SRCS = main.cpp
OBJS = $(SRCS:.cpp=.o)

# Output executable
TARGET = main

# Default target
all: $(TARGET)

# Link the executable
$(TARGET): $(OBJS)
	$(CXX) $(OBJS) -o $(TARGET) $(LDFLAGS)

# Compile source files
%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

# Clean up build files
clean:
	rm -f $(OBJS) $(TARGET)
