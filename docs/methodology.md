# Research Methodology

## Research Design

This study employed an experimental design to evaluate the feasibility of automating the manual "dotting" process used in colonial waterbird population surveys. The research followed a systematic approach combining geospatial data processing with machine learning model development and evaluation.

## Problem Statement

Colonial waterbird monitoring requires precise counting and species identification from aerial imagery. The current manual process involves expert ornithologists manually placing colored symbols (dots) on high-resolution images to mark individual birds or nests. This process is:
- Time-intensive (hundreds of dots per image)
- Labor-intensive (requires expert knowledge)
- Subjective (potential for human error/inconsistency)
- Resource-limiting (bottleneck for large-scale surveys)

## Methodology Framework

### Phase 1: Data Preparation and Analysis
1. **Historical Data Review**: Analyzed existing dotting datasets from May-June 2025 surveys
2. **Symbology Analysis**: Documented inconsistencies in symbol usage across survey sites
3. **Data Integration**: Merged feature classes from multiple survey locations
4. **Quality Assessment**: Evaluated data completeness and annotation quality

### Phase 2: Machine Learning Pipeline Development
1. **Architecture Selection**: Compared YOLOv3 vs FasterRCNN for object detection tasks
2. **Data Preprocessing**: 
   - Created bounding box annotations from point features
   - Generated image chips with consistent dimensions
   - Organized training/validation datasets
3. **Model Configuration**: Optimized hyperparameters through iterative testing
4. **Training Protocol**: Implemented transfer learning from COCO pretrained weights

### Phase 3: Evaluation and Optimization
1. **Performance Metrics**: Tracked mAP, precision, recall, and loss curves
2. **Convergence Analysis**: Monitored training stability and early stopping criteria
3. **Error Analysis**: Investigated failure cases and false positive/negative patterns
4. **Comparative Assessment**: Benchmarked multiple model configurations

## Technical Implementation

### Object Detection Approach
- **Framework**: ArcGIS Deep Learning Tools with PyTorch backend
- **Model Architecture**: FasterRCNN with ResNet50 backbone
- **Input Processing**: 256x256 and 512x512 pixel chips
- **Annotation Format**: ESRI feature classes converted to YOLO/COCO formats

### Training Strategy
- **Transfer Learning**: Leveraged COCO dataset pretrained weights
- **Data Split**: 80% training, 20% validation
- **Augmentation**: Geometric transformations only (preserve ecological context)
- **Loss Function**: Combined classification and bounding box regression loss

### Experimental Controls
- **Consistent Hardware**: NVIDIA GPU with 8GB+ VRAM
- **Standardized Metrics**: mAP@IoU=0.5 as primary evaluation metric
- **Reproducible Pipeline**: Documented all parameter settings and random seeds
- **Version Control**: Tracked model iterations and configuration changes

## Data Collection and Processing

### Source Data Characteristics
- **Temporal Scope**: May-June 2025 breeding season surveys
- **Geographic Coverage**: Gulf Coast colonial waterbird sites
- **Image Resolution**: Variable (drone and fixed-camera sources)
- **Annotation Quality**: Expert ornithologist validation

### Processing Pipeline
1. **Mosaic Creation**: Stitched individual images into seamless composites
2. **Georeferencing**: Aligned imagery to NAD83 Louisiana South coordinate system
3. **Feature Extraction**: Converted point annotations to bounding box training data
4. **Data Validation**: Cross-referenced annotations with field survey notes

## Limitations and Constraints

### Technical Limitations
- **Computational Resources**: Limited to single GPU training (8-12 hour sessions)
- **Dataset Size**: Relatively small training set compared to typical deep learning applications
- **Image Variability**: Inconsistent lighting, resolution, and viewing angles
- **Annotation Inconsistency**: Variable symbology across survey teams and time periods

### Methodological Constraints
- **Ground Truth Quality**: Manual annotations subject to human error and subjectivity
- **Species Complexity**: Difficulty distinguishing similar species from aerial imagery
- **Temporal Limitations**: Single breeding season data (limited seasonal variation)
- **Geographic Scope**: Focused on Gulf Coast ecosystems (limited habitat diversity)

## Quality Assurance

### Data Validation
- Cross-reference with field survey counts
- Expert review of training annotations
- Consistency checks across survey sites
- Statistical validation of annotation patterns

### Model Validation
- K-fold cross-validation consideration (limited by dataset size)
- Hold-out test set evaluation
- Visual inspection of detection results
- Comparison with manual counting accuracy

## Ethical Considerations

### Data Privacy
- Geospatial coordinates generalized to protect sensitive colony locations
- Survey site names anonymized in public documentation
- Collaboration agreements with data collection partners
- Restricted access to raw imagery datasets

### Environmental Impact
- Research supports conservation objectives
- Non-invasive monitoring methodology
- Reduced human disturbance through automation
- Improved efficiency for long-term population monitoring

## Future Research Directions

Based on initial findings, recommended next steps include:
1. **Dataset Expansion**: Multi-year, multi-site data collection
2. **Symbol Standardization**: Develop consistent annotation protocols
3. **Hierarchical Classification**: Species-specific model development
4. **Integration Testing**: Real-world deployment pilot programs
5. **User Interface Development**: GIS professional workflow integration